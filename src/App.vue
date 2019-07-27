<template>
  <div id="app">
    <Header />
    v-if="txtoutput !== ''"
    <Design :txtinput="txtinput" :txt_output="txtoutput"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Design from './components/Design.vue'

export default {
  name: 'app',
  components: {
    Header,
    Design
  },
  data() {
    return {
      txtinput: "",
      txtoutput: ""
    }
  },methods: {
    translate(){
      
    }
  },
  mounted: function(){
    fetch("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190722T062110Z.5f5465fc8ae5efb9.4218583f102455773fa9f2e8146c8928e25a37f6&lang=en-fa&text=hello", {
      method:"get"
    })
    .then((response) => {
      return response.json()
    })
    .then((jsonData) => {
      this.txtoutput = jsonData.text[0];
    })
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
