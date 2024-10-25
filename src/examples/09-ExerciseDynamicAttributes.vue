<script>
export default {
  data() {
    return {
      textColor: "red",

      postItColor: "yellow",
      header: "Mi post-it",
      item1: '• Hacer las compras',
      item2: '• Ir a la Salle',
      item3: '• Etc.',
      colorArray: ["blue", "red", "green", "yellow", "pink", "orange", "purple", "brown"] 
    }
  },
  methods: {
    changeTextColor(e) {
      var target = e.target;
      console.log(target.style.backgroundColor);
      this.textColor = target.style.backgroundColor
    },

    changePostItColor(e) {
      var target = e.target;
      console.log(target.style.backgroundColor);
      let newColor = this.postItColor
      while (newColor == this.postItColor){
        console.log(Math.floor(Math.random() * this.colorArray.length) );
        newColor = this.colorArray[Math.floor(Math.random() * this.colorArray.length)]
      }
      this.postItColor = newColor
    }
  }
}
</script>

<template>
  <p :style="{color: textColor}" >Text for testing!</p>

<div class="parent" style="display: grid; ">
  <div @click="changeTextColor" class="colorBox" style="background-color: #FFCDD2 ;"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #F8BBD0"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #C5CAE9;"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #C8E6C9;"></div>
</div>
<div class="parent" style="display: grid; ">
  <div @click="changeTextColor" class="colorBox" style="background-color: #F44336;"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #E91E63"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #3F51B5;"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #4CAF50;"></div>
</div>
<div class="parent" style="display: grid; ">
  <div @click="changeTextColor" class="colorBox" style="background-color: #B71C1C"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #880E4F"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #1A237E"></div>
  <div @click="changeTextColor" class="colorBox" style="background-color: #1B5E20;"></div>
</div>

<br><br>

<div @mouseover="changePostItColor" class="post-it" :style="{backgroundColor: postItColor}">
  <h1>{{ header }}</h1>
  <ul>
    <li>{{ item1 }}</li>
    <li>{{ item2 }}</li>
    <li>{{ item3 }}</li>
  </ul>
</div>

</template>

<style scoped>
.parent {
    display: grid;
    grid-template-columns: 100px 100px 100px 100px;
  }

.textColor {
  color: red;
}

.colorBox {
  margin: 1px;
  width: 100px;
  height: 100px;
}

.post-it {
  padding: 30px 40px;
  margin: 10px 10px;
  display: inline-block;
}

h1 {
  font-size: 20px;
  margin-bottom: 5px;
  padding: 20px 20px
}

li {
  font-weight: bold;
  margin-left: 5px;
}

</style>