<script setup>
import NewUser from './newuser.vue'
</script>

<template>
  <h4>Child component</h4>
  <h5>{{ name }}</h5>
  <h5>{{ email }}</h5>
  <NewUser v-for="user in users" :key="user" :user="user" :getReadStatus="getReadStatus" />
</template>

<script>
export default {
  name: 'ChildComponent',
  props: {
    name: String,
    email: String,
    users: Object
  },
  methods: {
    getReadStatus(status) {
      alert('Read: ' + status)
    }
  },
  components: { NewUser }
}
</script>
