<template>
    
        <div id="value" v-for="running in run" :key="running">Live<a v-bind:href="running.streams.official.raw_url">

                 {{ running.name }} <img v-bind:src="running.league.image_url" />
           </a>
       </div>
     

</template>

<script>
import axios from "axios";
export default {
    name: 'liveInformation',
    props: {
        running: String[Object],
        
    },
    
    data() {
        return {
            run: null,
            
        }
    },

    mounted() {

        axios
            .get('https://api.pandascore.co/lol/matches/running?sort=&per_page=2&token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ' )
            .then(response => this.run = response.data)
            .then(response => console.log(response))

       
    }
}




</script>

<style scoped>
#value img {
    max-width: 50px;
    max-height: 50px;
}



#value {
    float: left;
    width: 12%;
    height: 80px;
    color: red;
    border-style: solid;
    border-width: 3px;
    border-right-width: 1.5px;
    border-left-width: 1.5px;
    border-left-color: red;
    border-right-color: red;
    border-top-color: black;
    border-bottom-color:black ;
     background-color: grey;
}
</style>