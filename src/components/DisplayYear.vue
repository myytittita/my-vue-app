<template>
    <h2>🗓️ Here is what happened 🤓</h2>
    <ul>
        <li v-for="(fact, index) in yearfacts" v-bind:key="index">
            <div>
                {{ fact }}
            </div>
        </li>
    </ul>
</template>

<script>
export default {
    name: 'DisplayYear',
    props: ['yearfacts'],
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
    position: absolute;
    width: 45%;
    height: 70px;
}
</style>