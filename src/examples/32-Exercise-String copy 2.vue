<script>
export default {
  data() {
    return {
      myArray: ['a','b','c'],
      myString: ""
    }
  }
}
</script>

<template>
  <p>
    {{ myArray.join("-") }}
  </p>
</template>
