<template>
  <h2>Email: {{ email }}</h2>
  <h2>Username: {{ username }}</h2>
  <h2>Account Status: {{ getStatus() }}</h2>
</template>

<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      username: 'Tester',
      email: 'test@tester.com',
      getStatus: function () {
        return 'Unverified'
      }
    }
  }
}
</script>

<style scoped>
h2 {
  color: hsla(160, 100%, 37%, 1);
}
</style>
