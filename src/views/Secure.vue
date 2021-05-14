<template>
  <div class="secure">
    <h1>This page is protected by auth</h1>
    <router-link to="/">Home</router-link>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.secure {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

</style>