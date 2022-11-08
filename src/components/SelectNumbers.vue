<template>
  <div>
    <input type="number" min="0" max="2022" step="1" placeholder="Enter Year" v-model="year"/>
    <button @click="getYearInfo">Search Events</button>
    <br>
  </div>
</template>

<script>
const baseUrl = 'http://numbersapi.com/';

export default {
  name: 'SelectNumbers',
  emits: ['addNewYearFact'],
  data() {
    return {
      year: ''
    }
  },
  
  methods: {
    getYearInfo() {
      let reqUrl = baseUrl + this.year.toString() + '/year';
      console.log(reqUrl);

      fetch(reqUrl)
        .then((response) => response.text())
        .then((text) => this.$emit('addNewYearFact', text));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div {
  text-align: center;
}
input, number {
  width: 500px;
  font-size: 70pt;
  text-align: center;
  border: none;
  border-radius: 10px;
  color: #a30157;
  opacity: .5;
}

button {
  display: block;
  margin: 0.5em auto;
  color:navy;
  font-weight: bolder;
  border-radius: 3em;
  background-color: #a30157;
  border: none;
  padding: 1em;
  font-size: 12pt;
  color: white;
  margin-top: 1em;
  margin-bottom: 30px;
}

button:hover {
  background-color: #c53f86;
  cursor: pointer;
}
</style>
