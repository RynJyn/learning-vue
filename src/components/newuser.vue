<template>
  <p>New User</p>
  <ul :class="{ read: read, unread: !read }">
    <li>Name: {{ user.name }}</li>
    <li>Email: {{ user.email }}</li>
    <button v-on:click="read = !read">Mark {{ read ? 'Unread' : 'Read' }}</button>
  </ul>
</template>

<script>
export default {
  name: 'NewUser',
  props: {
    user: Object
  },
  data() {
    return {
      read: false
    }
  }
}
</script>

<style scoped>
.unread li {
  font-weight: 600;
}

.read li {
  font-weight: normal;
}
</style>
