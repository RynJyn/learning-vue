<template>
  <form>
    <label for="username">
      <input
        type="text"
        id="username"
        name="username"
        placeholder="Username"
        v-model="form_data.username"
      />
    </label>
    <label for="password">
      <input
        type="password"
        id="password"
        name="password"
        placeholder="Password"
        v-model="form_data.password"
      />
    </label>
    <label for="email">
      <input type="email" id="email" name="email" placeholder="Email" v-model="form_data.email" />
    </label>
    <button type="button" v-on:click="runSignUp">Create Account</button>
  </form>
</template>

<script>
export default {
  name: 'ProjectSignUp',
  data() {
    return {
      form_data: {
        username: '',
        password: '',
        email: ''
      },
      errors: []
    }
  },
  methods: {
    runSignUp() {
      console.log(this.form_data)
      if (this.validateForm()) {
        this.postFormData()
      }
    },
    validateForm() {
      this.errors = []
      for (const item of this.form_data) {
        if (item !== '') {
          this.errors.push(item)
        }
      }

      return this.errors.length === 0
    },
    async postFormData() {
      const userInfo = JSON.stringify(this.form_data)
      const res = await fetch('http://localhost:3000/users/', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: userInfo
      })
      const json = await res.json()

      localStorage.setItem('user-info', userInfo)
      this.$router.push({ name: 'project' })

      console.log(json)
    }
  }
}
</script>
