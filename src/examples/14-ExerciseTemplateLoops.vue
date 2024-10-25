<script>
export default {
  data() {
    return {
      header: 'Mi to-do ',
      todos: ['Hacer las compras', 'Ir a la Salle', 'Apprender VUE', 'Escribir JavaScript'], 

      imgSources: ["https://flagsapi.com/BE/flat/64.png", "https://flagsapi.com/ES/flat/64.png", "https://flagsapi.com/GB/flat/64.png"],
      imgSrcs : [{src: "https://flagsapi.com/BE/flat/64.png", id: 0}, {src: "https://flagsapi.com/ES/flat/64.png", id:1}, {src: "https://flagsapi.com/GB/flat/64.png", id:4}]
    }
  },
  methods: {
    removeImg(index){
      console.log(index)
      console.log(typeof(index));  
      this.imgSources.splice(index, 1)
    }
  }
}
</script>

<template>
   <div class="post-it" >
    <h1>{{ header }}</h1>
    <ul>
      <li v-for="item in todos" :key=item.id>   
        • {{ item }}
      </li>
    </ul>
  </div>

  <hr>
  <br>

  <div class="parent">
    <img v-for="(imgSource, index) in imgSources" :key="index" :src="imgSource" alt="" @click="removeImg(index)">
    
    <!-- <img v-for="imgSrc in imgSrcs" :key="imgSrc.id" :src="imgSrc.src" alt=""> -->



    <!-- <img class="imageBox" src="https://flagsapi.com/BE/flat/64.png" alt="">
    <img class="imageBox" src="https://flagsapi.com/ES/flat/64.png" alt="">
    <img class="imageBox" src="https://flagsapi.com/GB/flat/64.png" alt=""> -->
  </div>

</template>

<style scoped>
.post-it {
  background: yellow;
  padding: 50px 50px;
  margin: 50px 50px;
}

h1 {
  font-size: 20px;
  margin-bottom: 5px;
}

li {
  font-weight: bold;
}


.parent {
    display: grid;
    grid-template-columns: 100px 100px 100px;
  }

.imageBox {
  margin: 1px;
  width: 100px;
  height: 100px;
}
</style>