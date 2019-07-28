<template>
  <div id="app">
    <Header />
    <Design :txt_input="txtinput" :txt_output="txtoutput" :select_from="selectfrom" :select_to="selectto" v-on:fetch="updateVal($event)"
    v-on:sel_from="from($event)" v-on:sel_to="to($event)"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Design from './components/Design.vue'
import axios from "axios";

export default {
  name: 'app',
  components: {
    Header,
    Design
  },
  data() {
    return {
      txtinput: "",
      txtoutput: "Translated Text Place",
      selectfrom:"en",
      selectto: "fa"
    }
  },methods:{
    from(val){
      this.selectfrom = val;
      axios.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190722T062110Z.5f5465fc8ae5efb9.4218583f102455773fa9f2e8146c8928e25a37f6&lang=" 
        + this.selectfrom + "-" + this.selectto + "&text=" + this.txtinput)
        .then(response => {
          if(this.txtinput === "")
          {
            this.txtoutput = "Translated Text Place"
          }
          this.txtoutput = response.data.text[0];
        });
    },to(val){
      this.selectto = val;
      axios.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190722T062110Z.5f5465fc8ae5efb9.4218583f102455773fa9f2e8146c8928e25a37f6&lang=" 
        + this.selectfrom + "-" + this.selectto + "&text=" + this.txtinput)
        .then(response => {
          if(this.txtinput === "")
          {
            this.txtoutput = "Translated Text Place"
          }
          this.txtoutput = response.data.text[0];
        });
    },
    updateVal(val){
      this.txtinput = val;
      axios.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190722T062110Z.5f5465fc8ae5efb9.4218583f102455773fa9f2e8146c8928e25a37f6&lang=" 
        + this.selectfrom + "-" + this.selectto + "&text=" + this.txtinput)
        .then(response => {
          if(this.txtinput === "")
          {
            this.txtoutput = "Translated Text Place"
          }
          this.txtoutput = response.data.text[0];
        });
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
img {
  height: 300px;
  width: 300px;
}
</style>
