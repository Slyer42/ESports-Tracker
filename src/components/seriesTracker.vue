<template>
    <div id="selelct" class="Series">
        <select v-model="seriesList">
            <option>Alle Serien</option>
            <option>Laufende Serien</option>
            <option>Kommende Serien</option>
        </select>
    </div>
    <div id="Data1" v-if="seriesList == 'Alle Serien'">
        <div id="value1" v-for="running in location1" :key="running.url">
            <a v-bind:href="running.url">
                <div > 
                    <img v-bind:src="running.image_url" />
                    {{ running.name }}
                </div>
            </a>
        </div>
    </div>
    <div id="Data1" v-if="seriesList == 'Kommende Serien'">
        <div id="value1" v-for="coming in location2" :key="coming">
           <div > 
                <a v-bind:href="coming.league.url">
                    <img v-bind:src="coming.league.image_url" />
                    {{ coming.league.name }}
                
           </a> </div>
        </div>
    </div>
    <div id="Data1" v-if="seriesList == 'Laufende Serien'">
        <div id="value1" v-for="past in location3" :key="past">
            <a v-bind:href="past.league.url">
                <div>
                    <img v-bind:src="past.league.image_url" />
                    {{ past.league.name }}
                </div>
            </a>
        </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
    name: 'seriesTracker',
    props: {
        running: String[Object],
        coming: String[Object],
        past: String[Object],
        image: { url: "" },

    }
    , data() {
        return {
            location1: null,
            location2: null,
            location3: null,
            infos: null,
            seriesList: "",



        }
    },
    created() {
        axios
            .get('https://api.pandascore.co/lol/leagues?search[url]=https&token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ')
            .then(response => this.location1 = response.data)
            .then(response => console.log(response))

        axios
            .get('https://api.pandascore.co/lol/series/upcoming?token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ')
            .then(response => this.location2 = response.data)
            .then(response => console.log(response))

        axios
            .get('https://api.pandascore.co/lol/series/running?token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ',)
            .then(response => this.location3 = response.data)
            .then(response => console.log(response))


    },
    
    



}








</script>
<style scoped >
#Data1 div {
    height: 70px;
    
}

#Data1 img {
    max-width: 50px;
    max-height: 50px;
    padding-right: 30px;
    padding-top: 10px;
}
#Data1 {
    width: 50%;
    min-height: 30px;
    margin-top: 50px;
    margin: auto;
}
#value1 {
    border-style: solid;
    border-width: 2px;
    border-bottom-width: 1px;
    border-top-width: 1px;
    text-align: center;
    border-color: black;
}
#value1:hover {
    border-color: blue;
}


</style>