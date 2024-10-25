<script>
export default {
  data() {
    return {
      name: 'John',
      count: 0
    }
  }, 
  beforeCreate(){
    console.log("before created");
  },
  created() {
    console.log("created");
    console.log(`Component created by ${this.name}`)
  },
  mounted() {
    console.log("mounted");
    console.log(`Component mounted by ${this.name}`)
  },
  updated() {
    console.log("updated");   
  },
  unmounted() {
    console.log("unmounted");
    console.log(`Component unmounted by ${this.name}`)
  },
  beforeMount() {
    console.log("before mount");
  }
}
</script>

<template>
  <p>My name is: {{ name }}.</p>
</template>

<style scoped>
</style>