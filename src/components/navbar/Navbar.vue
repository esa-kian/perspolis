<template>
  <div class="navbar">
    <ul>
      <li>
          <router-link :to="'/'">
            Home
          </router-link>      
      </li>
      <li v-if="!authenticated">
          <router-link :to="'/login'">
            Login
          </router-link>
      </li>
      <li v-if="!authenticated">
          <router-link :to='"/register"'>
            Register
          </router-link>      
      </li>
      <li v-if="authenticated">
          <router-link :to="'/profile'">
              Profile
          </router-link>
        </li>
        
    </ul>
    
  </div>
</template>

<script>

  export default {
    mounted(){
      this.authenticated = localStorage.authenticated;
    },
    methods:{
     
    },
    data: () => ({
      drawer: false,
      group: null,
    }),
  }
</script>

<style scoped>
.navbar{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 60px;
    font-size: 16px;
    font-weight: 600;
    padding: 20px 40px;
    z-index: 999;
    backdrop-filter: blur(5px);
}
ul{
  display: flex;
  list-style-type: none;
  gap: 30px;
  width: 100%;

}
a{
  text-decoration: none;
}
</style>