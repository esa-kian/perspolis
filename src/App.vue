<template>
  <div id="app">
    <navbar></navbar>
    <transition name="fade">
    <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import Navbar from './components/navbar/Navbar.vue';


export default {
  name: 'App',
  components:{
    Navbar
    
    },
    mounted(){
      this.authenticated = localStorage.authenticated;
    },
  data: () => ({
  }),
};
</script>
<style scoped>
#app{
  font-family: sans-serif;
  background-image: linear-gradient(rgba(78, 0, 131, 0.212),rgba(45, 30, 58, 0.212), rgba(100, 110, 250, 0.26));
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
