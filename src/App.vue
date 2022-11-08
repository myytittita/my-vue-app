<template>
  <h1>Find historical events in...</h1>
  <SelectNumbers @add-new-year-fact="addNewYearFact"/>
  <DisplayYear :yearfacts="yearfacts"/>
</template>

<script>
import SelectNumbers from './components/SelectNumbers.vue'
import DisplayYear from './components/DisplayYear.vue'

export default {
  name: 'App',
  data() {
    return {
      yearfacts: []
    }
  },
  components: {
    SelectNumbers,
    DisplayYear
  },
  methods: {
    addNewYearFact(text) {
      this.yearfacts.push(text);
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
