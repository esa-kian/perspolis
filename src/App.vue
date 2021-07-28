<template>
  <div id="app">
    <navbar></navbar>
    <router-view></router-view>
  </div>
</template>

<script>
import Navbar from './components/navbar/Navbar.vue';


export default {
  name: 'App',
  components:{
    Navbar
    
    },
  data: () => ({
    //
  }),
};
</script>
<style scoped>
#app{
  font-family: sans-serif;
  background-image: linear-gradient(rgba(153, 0, 255, 0.76), rgba(172, 109, 224, 0.685), rgb(100, 110, 250));
}
</style>
