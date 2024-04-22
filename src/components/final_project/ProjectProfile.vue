<template>
  <h2>Welcome!</h2>
  <button type="button" v-on:click="logout">Logout</button>
</template>

<script>
export default {
  methods: {
    logout() {
      console.log('Logging out')
      localStorage.removeItem('user-info')
      this.$router.push({ name: 'project' })
    }
  }
}
</script>
