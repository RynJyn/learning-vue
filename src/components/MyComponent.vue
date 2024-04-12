<template>
  <h2>Email: {{ email }}</h2>
  <h2>Username: {{ username }}</h2>
  <h2>Account Status: {{ getStatus() }}</h2>
  <h2>Name: {{ getName('Tester') }}</h2>
  <h2>Data : {{ getData() }}</h2>
  <button v-on:click="myClick()">Click Here</button>
  <input type="text" v-model="count" />
  <h3>{{ count }}</h3>
</template>

<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      username: 'Tester',
      email: 'test@tester.com',
      count: 0
    }
  },
  methods: {
    getName(name) {
      return name
    },
    getData() {
      return {
        email: 'test@tester.com',
        username: 'tester',
        name: 'Tester'
      }
    },
    getStatus: function () {
      return 'Unverified'
    },
    myClick: function () {
      console.warn('Ouch!')
    }
  }
}
</script>

<style scoped>
h2 {
  color: hsla(160, 100%, 37%, 1);
}
</style>
