<template>
  <div>
    <input type="number" min="0" step="1" placeholder="Random year" v-model="year"/>
    <button @click="handleNewItem">Find Fact</button>
  </div>
</template>

<script>
export default {
  name: 'SelectNumbers',
  data() {
    return {
      year: ''
    }
  },
  emits: ['addRandomYear'],
  methods: {
    handleNewItem() {
      this.$emit('addRandomYear', this.year);
      this.year = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  text-align: center;
}

input, button {
  display: block;
  margin: 0.25em auto;
  color: black;
  font-weight: bolder;
}
</style>
