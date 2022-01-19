<template>
  <div id="nav">
    <router-link to="/">Home</router-link> 
   <link rel="icon" type="image/png" href="(../assets/lol.jpg">
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
#nav img {
  max-width: 150px;
  max-height: 140px;
}
</style>
