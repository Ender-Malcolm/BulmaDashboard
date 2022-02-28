<script>
export default {
    data() {
        return {
            city: ""
        }
    },

    async mounted() {

        //Async-Await Based Way
        const response = await fetch("https://api.openweathermap.org/data/2.5/weather?zip=16648,us&appid=431d09d780e3c761a8589f7bd5273fe0&units=imperial")
        const data = await response.json()

        this.city = data.name

    }
}
</script>


<template>
    <section class="info-tiles">
        <div class="tile is-ancestor has-text-centered">
            <div class="tile is-parent">
                <article class="tile is-child box">
                    <p class="title">{{ city }}</p>
                    <p class="subtitle">Weather Address</p>
                </article>
            </div>
        </div>
    </section>
</template>