<script setup>
import ChildComponent from './child.vue'
</script>

<template>
  <h3>Loops</h3>
  <ul>
    <li v-for="language in languages" :key="language">{{ language }}</li>
  </ul>
  <ul v-for="user in users" :key="user">
    <li>Name: {{ user.name }}</li>
    <li>Email: {{ user.email }}</li>
    <li v-if="user.verified">Verified</li>
  </ul>
  <ChildComponent name="Tony Stark" :email="childComponent.email" :users="users" />
</template>

<script>
export default {
  name: 'ForLoop',
  data() {
    return {
      languages: ['PHP', 'JavaScript', 'C++', 'C#'],
      users: [
        {
          name: 'Tester',
          email: 'tester@test.com',
          verified: false
        },
        {
          name: 'Admin',
          email: 'admin@admin.com',
          verified: true
        }
      ],
      childComponent: {
        email: 'tony@gmail.com'
      }
    }
  },
  components: { ChildComponent }
}
</script>
