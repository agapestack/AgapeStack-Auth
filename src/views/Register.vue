<template>
  <div>
    
    <form @submit.prevent="register" class="register">
      <h1>Register</h1>

      <label for="username">Username</label>
      <div>
          <b-form-input id="username" type="text" v-model="username" required autofocus/>
      </div>

      <label for="email" >E-Mail Address</label>
      <div>
          <b-form-input id="email" type="email" v-model="email" required/>
      </div>

      <label for="password">Password</label>
      <div>
          <b-form-input id="password" type="password" v-model="password" required/>
      </div>

      <label for="password-confirm">Confirm Password</label>
      <div>
          <b-form-input id="password-confirm" type="password" v-model="password_confirmation" required/>
      </div>

      <br>
      <hr>
      <div>
          <b-button type="submit">Register</b-button>
      </div>
      <br>
      <router-link to="/login">Already registered? </router-link>
      <router-link to="/">Home</router-link>
    </form>
  </div>
</template>

<script>
export default {
  name: "Register",
  data() {
    return {
      username: "",
      email: "",
      password: "",
      password_confirmation: "",
    }
  },
  methods: {
    register: function() {
      let data = {
        username: this.username,
        email: this.email,
        password: this.password
      }
      console.log(username)
      this.$store.dispatch('register', data)
        .then(() => this.$router.push('/'))
        .catch(err => console.log(err))
    }
  }
}
</script>

<style scoped>
form.register {
  display: flex;
  flex-direction: column;
  border: 1px solid white;
  padding: 3rem;
  border-radius: 10px;
}
</style>