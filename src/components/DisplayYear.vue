<template>
    <!-- create a dropdown for all the years searched -->
    <!-- create a local data property called 'currentYear' -->
    <!-- use currentYear to pick which list of facts to show -->
    <select v-if="!!currentYear" v-model="currentYear">
        <option v-for="(facts, year, index) in yearfacts" v-bind:key="index">
            <div @click="getCurrentYear">
                {{ year }}
            </div>
        </option>
    </select>

    <h2>🗓️ Here is what happened 🤓</h2>
    <ul v-if="!!currentYear">
        <li v-for="(fact, index) in yearfacts[currentYear]" v-bind:key="index">
           {{ fact.text }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'DisplayYear',
    props: ['years', 'yearfacts'],
    data() {
        return {
            currentYear: null
        }
    },
    watch: {
        years: {
            handler: function(years) {
                this.currentYear = years[years.length - 1];
            },
            deep: true
        }
    }

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
    height: fit-content;
}
</style>