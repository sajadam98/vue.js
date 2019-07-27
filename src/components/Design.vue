<template>
  <div id="root">
    <img alt="Vue logo" src="../assets/logo.png" />
    <form>
      <div class="text-input">
        <label for="text_input" id="label-input"><b>Text :</b></label>
        <textarea
          type="text"
          class="text-input-control"
          id="txt-input"
          aria-describedby="text-input"
          placeholder="Enter Text"
          v-model="txtinput"
        />
      </div>
      <button type="submit" class="btn btn-primary" >Translate</button>
    </form>
    <div class="spinner-border" role="status">
      <span class="sr-only">Loading...</span>
    </div>
    <div>
      <ul id="txt_translation">{{txt_output}}</ul>
    </div>
  </div>
</template>
<script>
export default {
  props:{
    txtinput: String,
    txt_output: String,
    translate: Function
  }
}
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
  background-color: darkgray;
  color: aliceblue;
  font-family: Arial, Helvetica, sans-serif;
}
#root {
  width: 100%;
  height: 100%;
  background-color: #fff8e1;
}
#about-us-title{
  color: blue
}
#about-us-link{
  color: blue;
  font-size: 19px;
  margin-left: 100px
}
</style>
