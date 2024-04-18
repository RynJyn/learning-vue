<template>
  <p>New User</p>
  <ul>
    <li>Name: {{ user.name }}</li>
    <li>Email: {{ user.email }}</li>
  </ul>
</template>

<script>
export default {
  name: 'NewUser',
  props: {
    user: Object
  }
}
</script>
