<template>
  <h1>Interesting Fact about years</h1>
  <SelectNumbers @add-random-year="addRandomYear"/>
  <DisplayYear @delete-year="deleteYear" v-model:yearnumber="yearnumber"/>
</template>

<script>
import SelectNumbers from './components/SelectNumbers.vue'
import DisplayYear from './components/DisplayYear.vue'

export default {
  name: 'App',
  data() {
    return {
      yearnumber: []
    }
  },
  components: {
    SelectNumbers,
    DisplayYear
  },
  methods: {
    addRandomYear(year) {
      console.log(year);
      this.yearnumber.push(year);
    },
    deleteYear(index) {
      this.yearnumber.splice(index, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 1em auto;
}
</style>
