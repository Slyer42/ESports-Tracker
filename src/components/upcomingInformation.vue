<template>
    <div id="value" v-for="running in run" :key="running">
        Next
        <a v-bind:href="running.streams.official.raw_url">{{ running.name }}
        <img v-bind:src="running.league.image_url" /></a>
    </div>
</template>

        <script>
import axios from "axios";
export default {
    name: 'upcomingInformation',
    props: {
        running: String[Object],
    },
    
    data() {
        return {
            run: null
        }
    },

    mounted() {
        axios
            .get('https://api.pandascore.co/lol/matches/upcoming?sort=&per_page=6&token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ')
            .then(response => this.run = response.data)
            .then(response => console.log(response))
    }
}
</script>

        <style scoped>
#value img {
    max-width: 50px;
    min-height: 50px;
}
#data {
    vertical-align: top;
}
#value {
    float: left;
    width: 12%;
    height: 80px;
    color: white;
    border-style: solid;
    border-width: 3px;
    border-right-width: 1.5px;
    border-left-width: 1.5px;
    border-color: black;
    background-color: rgba(128, 128, 128, 0.589);
    
}
</style>