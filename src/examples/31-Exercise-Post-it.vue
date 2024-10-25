<script>
export default {
  data() {
    return {
      header: 'Mi to-do ',
      bullet1: 'Hacer las compras',
      bullet2: 'Ir a la Salle',
      bullet3: 'Etc.'
    }
  }
}
</script>

<template>
  <div class="post-it" >
    <h1>{{ header }}</h1>
    <ul>
      <li>• {{ bullet1 }}</li>
      <li>• {{ bullet2 }}</li>
      <li>• {{ bullet3  }}</li>
    </ul>

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
</style>