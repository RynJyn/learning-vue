<template>
  <h3>Sign Up</h3>
  <form>
    <label for="username">
      Username:
      <input
        type="text"
        id="username"
        name="username"
        placeholder="Username"
        v-model="form.username"
      />
    </label>
    <label for="password">
      Password:
      <input
        type="password"
        id="password"
        name="password"
        placeholder="Password"
        v-model="form.password"
      />
    </label>
    <fieldset>
      <legend>Hobbies:</legend>
      <label for="sports">
        <input type="checkbox" id="sports" value="Sports" v-model="form.hobbies" />
        Sports
      </label>
      <label for="music">
        <input type="checkbox" id="music" value="Playing Music" v-model="form.hobbies" />
        Playing Music
      </label>
      <label for="gardening">
        <input type="checkbox" id="gardening" value="Gardening" v-model="form.hobbies" />
        Gardening
      </label>
    </fieldset>
    <fieldset>
      <legend>Gender</legend>
      <label for="male">
        <input type="radio" id="male" name="gender" value="Male" v-model="form.gender" />
        Male
      </label>
      <label for="female">
        <input type="radio" id="female" name="gender" value="Female" v-model="form.gender" />
        Female
      </label>
      <label for="other">
        <input type="radio" id="other" name="gender" value="Other" v-model="form.gender" />
        Other
      </label>
      <label for="optout">
        <input
          type="radio"
          id="optout"
          name="gender"
          value="Prefer not to say"
          v-model="form.gender"
        />
        Prefer not to say
      </label>
    </fieldset>
    <button type="button" v-on:click="signup">Sign Up</button>
  </form>
  <ul v-if="errors.length > 0">
    <li v-for="error in errors" :key="error">Please fill in: {{ error }}</li>
  </ul>
</template>

<script>
export default {
  name: 'SignUpForm',
  data() {
    return {
      form: {
        username: '',
        password: '',
        hobbies: [],
        gender: ''
      },
      errors: []
    }
  },
  methods: {
    signup() {
      this.errors = []
      for (const item in this.form) {
        if (this.form[item] === '' || this.form[item].length === 0) {
          this.errors.push(item)
        }
      }
      console.table(this.form, this.errors)
    }
  }
}
</script>
