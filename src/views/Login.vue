<template>
 <div>
  <form class="login" @submit.prevent="login">

      <h1>Sign in</h1>
    
    <br />
    <label>Email</label>
    <b-form-input required v-model="email" type="email" placeholder="Email"/>
    <label>Password</label>
    <b-form-input required v-model="password" type="password" placeholder="Password"/>


    <br/>
    <hr/>
    <b-button type="submit">Login</b-button>

    <br/>
    <router-link to="/register">Not Account? register now!</router-link>
    <router-link to="/">Home</router-link>
     
   </form>
 </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    }
  },
  methods: {
    login: function () {
      let email = this.email
      let password = this.password
      this.$store.dispatch('login', { email, password })
        .then(() => this.$router.push('/'))
        .catch(err => console.log(err))
    }
  }
}
</script>

<style scoped>
form.login {
  display: flex;
  flex-direction: column;
  border: 1px solid white;
  padding: 3rem;
  border-radius: 10px;
}

</style>