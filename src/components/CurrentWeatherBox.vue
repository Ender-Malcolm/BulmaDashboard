<script>

export default {

    props: {
        zipCode: String
    },

    data() {
        return {
            currentTemp: 0,
            feelsLike: 0,
            windDir: 0,
            windSpeed: 0,
            windGust: 0,
            sky: "",
            skyDesc: "",
            humidity: 0,
            pressure: 0,
        }
    },

    async mounted() {

        //Async-Await Based Way
        const response = await fetch("https://api.openweathermap.org/data/2.5/weather?zip=16648,us&APIKEY&units=imperial")
        const data = await response.json()
        this.currentTemp = data.main.temp
        this.feelsLike = data.main.feels_like
        this.windDir = data.wind.deg
        this.windSpeed = data.wind.speed
        
        this.windGust = data.wind.gust
        
        this.sky = data.weather[0].main
        this.skyDesc = data.weather[0].description
        this.humidity = data.main.humidity
        this.pressure = (data.main.pressure * 0.0145038).toFixed(2)

    }

}

</script>


<template>
    <div class="column is-6">
        <div class="card events-card">
            <header class="card-header">
                <p class="card-header-title">Current Weather</p>
                <a href="#" class="card-header-icon" aria-label="more options">
                    <span class="icon">
                        <i class="fa fa-angle-down" aria-hidden="true"></i>
                    </span>
                </a>
            </header>
            <div class="card-table">
                <div class="content">
                    <table class="table is-fullwidth is-striped">
                        <tbody>
                            <tr>
                                <td width="5%">
                                    <i class="fa"></i>
                                </td>
                                <td>Temp: {{ currentTemp }}&deg;F</td>
                                <td>Feels like: {{ feelsLike }}&deg;F</td>
                            </tr>
                            <tr>
                                <td width="5%">
                                    <i class="fa"></i>
                                </td>
                                <td>Wind: {{ windDir }}&deg; @ {{ windSpeed }}MPH</td>
                                
                                <td v-if="windGust">Gust: {{ windGust }}MPH</td>
                                <td v-else>Gust: No Gust</td>
                            </tr>
                            <tr>
                                <td width="5%">
                                    <i class="fa"></i>
                                </td>
                                <td>Sky: {{ sky }}</td>
                                <td>Description: {{ skyDesc }}</td>
                            </tr>
                            <tr>
                                <td width="5%">
                                    <i class="fa"></i>
                                </td>
                                <td>Humidity: {{ humidity }}%</td>
                                <td>Atmospheric Pressure: {{ pressure }}PSI</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>