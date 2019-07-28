<template>
  <div id="root">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div>
      <div class="text-input">
        <label for="text_input" id="label-input">
          <b>Text :</b>
        </label>
        <textarea
          type="text"
          class="text-input-control"
          id="txt-input"
          aria-describedby="text-input"
          placeholder="Enter Text"
          v-model="txt_input"
        />
      </div>
      <!-- <button class="btn btn-primary" v-on:click="translate">Translate</button> -->
    </div>
    <form style="margin-top: 30px;margin-bottom: 40px">
      <h style="display: inline">From :</h>
      <select id="select_from" style="display: inline" @change="onChange($event)">
        <option value="en" selected="selected">en</option>
        <option value="fa">fa</option>
        <option value="ar">ar</option>
        <option value="fr">fr</option>
      </select>
      <h style="display: inline;margin-left: 30px">To :</h>
      <select id="select_to" @change="onChange2($event)">
        <option value="en">en</option>
        <option value="fa" selected="selected">fa</option>
        <option value="ar">ar</option>
        <option value="fr">fr</option>
      </select>
    </form>
    <!-- <div class="spinner-border" role="status">
      <span class="sr-only">Loading...</span>
    </div>-->
    <div id="translatedplace">
      <ul id="txt_translation">
        <b>{{txt_output}}</b>
      </ul>
    </div>
    <div>
      <ul style="font-size:9px;margin-top:30px">Design By HajSajad<br><b>Derak</b></ul>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    txt_input: String,
    txt_output: String,
    select_from: String,
    select_to: String
  },
  // methods: {
  //   translate() {
  //     this.$emit("fetch", this.txt_input);
  //   }
  // },
  watch: {
    txt_input: function() {

      
        

      if (this.txt_input.length < 1) {

        this.$emit("fetch", "Translation");
      }
      this.$emit("fetch", this.txt_input);
    }
  },
  methods: {
    onChange(event) {
      this.$emit("sel_from" , event.target.value);
    },
    onChange2(event) {
      this.$emit("sel_to" , event.target.value);
    }
  }
};
</script>
<style>
.text-input {
  width: 20%;
  margin-left: 40%;
  margin-right: 40%;
}
#label-input {
  text-align: start;
  display: block;
  margin-top: 15px;
}
#txt-input {
  width: 100%;
  height: 150px;
  resize: none;
  font-size: 20px;
}
.btn {
  margin-top: 20px;
  width: 250px;
  border-radius: 10px;
}
#txt_translation {
  width: 30%;
  margin-left: 35%;
  margin-right: 35%;
  font-size: 20px;
  background-color: darksalmon;
  color: blue;
  font-family: Arial, Helvetica, sans-serif;
}
#root {
  width: 100%;
  height: 100%;
  background-color: #fff8e1;
}
#about-us-title {
  color: blue;
}
#about-us-link {
  color: blue;
  font-size: 19px;
  margin-left: 100px;
}
#translatedplace {
  margin-top: 20px;
}
</style>
