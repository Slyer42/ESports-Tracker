<template>
  <div class="item" id="value1">
    <liveInformation />
    <UpcomingInformation/>
  </div>

<div class="item2" id="value2">
  <button @click="visible = !visible ,  nosible = false">Serien Anzeigen</button>  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;         
  <button @click="nosible = !nosible , visible = false"  > Nach Teams suchen</button>
    <seriesTracker v-if="visible" />
    <SearchTeams v-if="nosible"  />
  </div>
</template>

<script>
import seriesTracker from "../components/seriesTracker.vue"
import liveInformation from "../components/liveInformation.vue"
import SearchTeams from "../components/searchTeams.vue"
import UpcomingInformation from "../components/upcomingInformation.vue"



// @ is an alias to /src




export default {
  name: 'Home',
  components: {
    seriesTracker,
    liveInformation,
    SearchTeams,
    UpcomingInformation
},
  data() {
    return {
      visible: false,
      nosible: false,

    }
  }, 
  



}





</script>

<style scoped>

#value2 {
  padding-top: 150px;
  
  
  
}
#value2 button{
  
  height: 100px;
  width: 250px;
  border-color: white;
  color: white;
  background-color: rgba(23, 23, 122, 0.685) ;
  
  
  
}
#value2 button:hover{
  height: 130px;
  width: 280;
  background-color:rgb(2, 41, 114);
}
#value2 button:focus{
  height: 130px;
  width: 280;
  background-color:rgb(2, 41, 114);
}


#value2  {
  text-align: center;
}
#template {
  background-color: grey;
}
</style>