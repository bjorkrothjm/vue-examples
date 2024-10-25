<script>
export default {
  data() {
    return {
      country1: "Spain",
      country2: "France",
      country3: "Portugal",
      country4: "United Kingdom",
      country5: "Italy",
      imageCountry: "",
      testText: "This is some text to try stuff out.",
      htmlTag: ""
    }
  },
  methods: {
    changeImage(e) {
      var target = e.target;
      console.log(target.innerHTML);
      this.imageCountry = target.innerHTML.toString();
    },
    editorModeToggle(e) {
      var target = e.target;
      console.log(target.tagName);
      var tag = target.tagName.toString();
      if (tag == "P") this.htmlTag = "INPUT"
      else this.htmlTag = "P"      
    }

  }
}
</script>

<template>
  <div style="display: flex; flex-direction: row;">
    <div>
      <button @click="changeImage" class="btn">{{ country1  }}</button>
      <button @click="changeImage" class="btn">{{ country2  }}</button>
      <button @click="changeImage" class="btn">{{ country3  }}</button>
      <button @click="changeImage" class="btn">{{ country4  }}</button>
      <button @click="changeImage" class="btn">{{ country5  }}</button>
    </div>
    <div>
      <div style="width:200px; vertical-align: middle;">
        <img v-if="imageCountry === country1" src="https://flagsapi.com/ES/flat/64.png" alt="" style="width:100%; height: 100%;">
        <img v-else-if="imageCountry === country2" src="https://flagsapi.com/FR/flat/64.png" alt="" style="width:100%; height: 100%;">
        <img v-else-if="imageCountry === country3" src="https://flagsapi.com/PT/flat/64.png" alt="" style="width:100%; height: 100%;">
        <img v-else-if="imageCountry === country4" src="https://flagsapi.com/GB/flat/64.png" alt="" style="width:100%; height: 100%;">
        <img v-else-if="imageCountry === country5" src="https://flagsapi.com/IT/flat/64.png" alt="" style="width:100%; height: 100%;">
        <img v-else src="https://flagsapi.com/BE/flat/64.png" alt="" style="width:100%; height: 100%;">
      </div>
    </div>
  </div>

  <hr>
  <br>

  <div>
    <!-- <span v-if="htmlTag === 'SPAN'" class="input" @click="editorModeToggle"> {{ testText }} </span>
    <p v-else @click="editorModeToggle">{{ testText }}</p> -->

    <!-- <input v-if="htmlTag === 'INPUT'" @dblclick="editorModeToggle" type="text"> -->
    <input v-if="htmlTag === 'INPUT'" @keyup.enter="editorModeToggle" type="text" class="input" v-bind:value="testText">
    <p v-else @click="editorModeToggle">{{ testText }}</p>

  </div>
</template>

<style scoped>

.btn{
  padding: 10px 15px;
  margin: 10px 10px;
  background-color: lightgray;
  display: block;
}

.input{
  border-style: solid;
  border-color: lightgrey;
  border-width: 1px;
  padding: 4px 4px;
  width: 90%;

}

</style>