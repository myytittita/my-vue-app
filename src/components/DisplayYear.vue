<template>
    <!-- create a dropdown for all the years searched -->
    <!-- create a local data property called 'currentYear' -->
    <!-- use currentYear to pick which list of facts to show -->
    <h2>🗓️ Here is what happened 🤓</h2>
    <ul v-for="(facts, year, index) in yearfacts" v-bind:key="index">
        <li v-for="(fact, index) in facts" v-bind:key="index">
           {{ fact.text }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'DisplayYear',
    props: ['years', 'yearfacts'],
}
</script>

<style scoped>
h2 {
    font-family: Arial, Helvetica, sans-serif;
    font-weight: 100;
    font-size: 14pt;
}

ul {
    list-style-type: none;
    width: 50%;
    margin: 0 auto;
    padding: 0;
}

li {
    padding: 0.25em;
    border-left: 10px solid #a30157;
    background-color: thistle;
    margin-bottom: 1em;
    padding: 40px;
    /* position: absolute; */
    width: 45%;
    height: 70px;
}
</style>