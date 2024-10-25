<script>
import { ref } from 'vue'
export default {
  setup () {
    const name = ref('John')
    const lastName = ref('Doe')
    const age = ref(55)
    return {
      name ,
      lastName,
      age
    }
  },
  mounted() {
    console.log(`The inital name is ${this.name}.`);
    console.log(`The inital last name is ${this.lastName}.`);
    console.log(`The inital age is ${this.age}.`);
  },
}
</script>

<template>
  <p>My name is: {{ name }} {{ lastName }} and my age is {{ age }}</p>
</template>

<style scoped>
p {
  font-weight: bold;
}
</style>
