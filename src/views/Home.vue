<template>
<div class="home">
  <h1>Home</h1>

  <b-nav>
    <b-nav-item><router-link to="/secure">Secure</router-link></b-nav-item>
    <b-nav-item><router-link to="/login" v-if="!isLoggedIn">Login</router-link></b-nav-item>
    <b-nav-item><router-link to="/register" v-if="!isLoggedIn">Register</router-link></b-nav-item>
    <b-nav-item v-if="isLoggedIn"><a @click="logout">Logout</a></b-nav-item>
  </b-nav>

</div>
</template>

<script>


export default {
  name: 'Home',
  methods: {
    logout: function () {
      this.$store.dispatch('logout')
      .then(() => {
        this.$router.push('/login')
      })
    }
  },
  computed : {
    isLoggedIn : function(){ return this.$store.getters.isLoggedIn}
  },
}
</script>

<style scoped>
.home {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}


</style>
