<script>

export default {

    data() {
        return {
            apiData: {},
            flag: false
        }
    },

    async mounted() {

        //Async-Await Based Way
        const response = await fetch("https://backendapisample.draketamer.repl.co/api")
            .then(async (response) => {
                this.apiData = await response.json()
                this.flag = true
            })
            .catch((error) => {
                console.log('api broke down...')
            })
    }
}
</script>

<template>
    <h1 v-if="flag">Some data from the api is <b>{{ apiData.food }}</b> in {{ apiData }}!</h1>
    <h1 v-else>The API is currently down, please try again later...</h1>
</template>

<style scoped>
h1 {
    color: antiquewhite;
    text-align: center;
    margin-bottom: 1rem;
    background: rgb(50, 96, 182);
}
</style>