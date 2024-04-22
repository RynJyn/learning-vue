<template>
  <h2>API</h2>
  <div v-if="Object.keys(info).length > 0" class="api-res">
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Forename</th>
          <th>Surname</th>
          <th>Email</th>
          <th>Avatar</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in info.data" :key="item">
          <td>{{ item.id }}</td>
          <td>{{ item.first_name }}</td>
          <td>{{ item.last_name }}</td>
          <td>{{ item.email }}</td>
          <td><img v-bind:src="item.avatar" /></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      info: {}
    }
  },
  async mounted() {
    const resp = await fetch('https://reqres.in/api/users?page=2')
    const json = await resp.json()
    this.info = json
  }
}
</script>
