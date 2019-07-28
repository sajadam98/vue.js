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
      <b-form-select v-model="selected_from" @change="onChange()" :options="options_from"></b-form-select>
      <h style="display: inline;margin-left: 30px">To :</h>
      <b-form-select v-model="selected_to" @change="onChange2()" :options="options_to"></b-form-select>
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
      <ul style="font-size:9px;margin-top:30px">
        Design By HajSajad
        <br />
        <b>Derak</b>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      selected_from: "en",
      selected_to: "fa",
      options_from: [
        { value: "en", text: "en" },
        { value: "fa", text: "fa" },
        { value: "ar", text: "ar" },
        { value: "fr", text: "fr" }
      ],
      options_to: [
        { value: "en", text: "en" },
        { value: "fa", text: "fa" },
        { value: "ar", text: "ar" },
        { value: "fr", text: "fr"}
      ]
    };
  },
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
    onChange() {
      this.$emit("sel_from", this.selected_from);
    },
    onChange2() {
      this.$emit("sel_to", this.selected_to);
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
