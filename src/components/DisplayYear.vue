<template>
    <h2>Random Year</h2>
    <ul>
        <li v-for="(year, index) in yearnumber" v-bind:key="index">
            <div>
                {{ year }}
            </div>
            <button @click="deleteYear(index)">✖</button>
        </li>
    </ul>
</template>

<script>
export default {
    name: 'DisplayYear',
    props: ['yearnumber'],
    emits: ['deleteYear'],
    methods: {
        deleteYear(index) {
            this.$emit('deleteYear', index);
        }
    }
}
</script>

<style scoped>
ul {
    list-style-type: none;
    width: 50%;
    margin: 0 auto;
    padding: 0;
}

li {
    padding: 0.25em;
    border-bottom: 2px groove coral;
    margin-bottom: 0.25em;
    display: flex;
    justify-content: space-between;
}
</style>