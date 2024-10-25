<script>
export default {
  data() {
    return {
      buttonText : "Click here",
      titleArray: ["Click ME!", "This is a button", "Click here", "Try to click?", "A button to click"],

      textText: "Text to hover over",
      newTextText: ["You just hovered", "Thank you for hovering"],
      myCount: 0,

      textText2:  "Text to hover over",
      newTextText2: ["Text to hover over", "Thank you for hovering"],
      myCount2: 0,
    }
  },
  methods: {
    changeButton(){
      let newText = this.buttonText
      while (newText == this.buttonText){
        console.log(Math.floor(Math.random() * this.titleArray.length) );
        newText = this.titleArray[Math.floor(Math.random() * this.titleArray.length)]
      }
      this.buttonText = newText
    },

    changeText(){
      this.myCount += 1;
      if (this.myCount%2==0) {
        this.textText = this.newTextText[1];
      }
      else {
        this.textText = this.newTextText[0];
      }
    },

    hoverText(){
      this.myCount2 += 1;
      if (this.myCount2%2==0) {
        this.textText2 = this.newTextText2[0];
      }
      else {
        this.textText2 = this.newTextText2[1];
      }

    }
  },
}
</script>

<template>
  <!-- <button v-on:click="changeText">{{ buttonText1 }}</button> -->
  <button @click="changeButton">{{ buttonText }}</button>
  <br><br>
  <p @mouseover="changeText">{{ textText }}</p>
  <br><br>
  <p @mouseout="hoverText" @mouseover="hoverText">{{ textText2 }}</p>
</template>


<style scoped>
button{
  background: lightgray;
  padding: 5px 10px;
  margin: 10px 10px;
}

h1 {
  font-size: 20px;
  margin-bottom: 5px;
}
p {
  font-size: 15px;
  font-weight: bold;
}

</style>

