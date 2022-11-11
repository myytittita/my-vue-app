<template>
  <h1>Find historical events in...</h1>
  <SelectNumbers @add-new-year-facts="addNewYearFacts"/>
  <DisplayYear :years="years" :yearfacts="yearfacts"/>
</template>

<script>
import SelectNumbers from './components/SelectNumbers.vue'
import DisplayYear from './components/DisplayYear.vue'

export default {
  name: 'App',
  data() {
    return {
      years: [],
      yearfacts: {}
    }
  },
  components: {
    SelectNumbers,
    DisplayYear
  },
  methods: {
    addNewYearFacts(data) {
      this.years.push(data.year);
      this.yearfacts[data.year] = data.facts;
      console.log(this.yearfacts);
    },
  }
}
</script>

<style>
body {
  background-color: lavender;
}
h1 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 22pt;
  font-weight:lighter;
  padding-top: 40px;
  padding-bottom: 30px;
}

#app {
  font-family: "Lucida Console", "Courier New", monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 1em auto;
}
</style>
