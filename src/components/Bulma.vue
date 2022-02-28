<script setup>
import LeftMenu from '@/components/LeftMenu.vue'
import WelcomeBox from '@/components/WelcomeBox.vue'
import AddressBox from '@/components/AddressBox.vue'
import CurrentWeatherBox from './CurrentWeatherBox.vue';
import CitySearchBox from './CitySearchBox.vue';
import Chart from './Chart.vue';
</script>

<template>
    <div class="container">
        <div class="columns">
            <LeftMenu />
            <div class="column is-9">
                <nav class="breadcrumb" aria-label="breadcrumbs">
                    <ul>
                        <li>Hello</li>
                        <li class="is-active">
                            <a href="#" aria-current="page">Weather</a>
                        </li>
                    </ul>
                </nav>

                <WelcomeBox />
                <AddressBox address="Earth, Solar System 001" />

                <div class="columns">
                    <CurrentWeatherBox />
                    <CitySearchBox />
                </div>
            </div>
        </div>
    </div>
    <Chart />
</template>