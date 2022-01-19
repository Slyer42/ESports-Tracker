<template>
    <div id="team">
        <input class="Suche" v-model="searchTeam" placeholder="Nach welchem Team suchst du?" />
        <button @click="showTeams()">Look up teams</button>
        <div v-if="searchTeam != ''">
            <div id="value" v-for="info in infos" :key="info">
                <img v-bind:src="info.image_url" />
                {{ info.name }}
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default
    {
        name: 'searchTeams',
        props: {
            info: String[Object],
        },
        
        data() {
            return {
                searchTeam: "",
                infos: null,
                infos2: null,

            }
        },

        methods: {
            showTeams() {
                axios
                    .get('https://api.pandascore.co/lol/teams?token=MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ ')
                    .then(response => this.infos = response.data)
                    .then(response => console.log(response))
            },
        }
    }

</script>

<style scoped>
#value img {
    max-width: 50px;
    max-height: 50px;
}
</style>