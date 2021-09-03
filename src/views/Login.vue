<template>
    <div class="main">
      <div class="login">

          <v-text-field
            class="my-btn"
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          ></v-text-field>
    
        
          <v-text-field
            class="my-btn"
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Password"
            hint="At least 8 characters"
            counter
            @click:append="show1 = !show1"
          ></v-text-field>
    
     
          <v-btn
            depressed
            color="primary"
            class="my-span"
            @click="login"
          >
            Login
          </v-btn>
          <span class="redirect">Don't have an account? 
            <router-link :to="'/register'">
            Sign up here.
            </router-link>
            </span>
       
      </div>

    </div>
  
</template>

<script>


  export default {
    methods:{
      login(){
        localStorage.authenticated = true;
        this.authenticated = true;

        this.$router.push('/profile');
        this.$router.go();

      }
    },
    data: () => ({
      valid: false,
      firstname: '',
      lastname: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
       show1: false,
        password: '',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => (`The email and password you entered don't match`),
        },
    }),
  }
</script>

<style scoped>
.v-btn{
  background: #8F00FF !important;
  transition: .2s ease;
}

.v-btn:hover{
  transition: .2s ease;
  background: #ffe712e5 !important;
  color: #48444b;
}

.main {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: auto;
}
.login{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  width: 300px;
  height: 400px;
  background-color: rgba(240, 248, 255, 0.425);
  backdrop-filter: blur(3px);
  padding: 20px 30px;
  transition: .2s ease;
  border-radius: 8px;
}
.login:hover{
  transition: .2s ease;
  background-color: rgba(240, 248, 255, 0.747);
   width: 320px;
  height: 420px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
.my-btn{
  width: 100%;
  font-weight: 700;
}
.my-span{
  font-weight: 700 !important;
}

span.redirect{
  margin-top:10px;
  font-size: 12px;
}
</style>