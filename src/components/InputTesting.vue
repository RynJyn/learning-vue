<template>
  <label>
    <input type="checkbox" value="cricket" v-model="sports" />
    Cricket
  </label>
  <label>
    <input type="checkbox" value="football" v-model="sports" />
    Football
  </label>
  <label>
    <input type="checkbox" value="hockey" v-model="sports" />
    Hockey
  </label>
  <label>
    <input type="radio" value="Smith" v-model="player" name="player" />
    Smith
  </label>
  <label>
    <input type="radio" value="Finch" v-model="player" name="player" />
    Finch
  </label>
  <h3>Selected Sports: {{ sports }}</h3>
  <h3>Selected Player: {{ player }}</h3>
</template>

<script>
export default {
  name: 'InputTesting',
  data() {
    return {
      sports: [],
      player: ''
    }
  }
}
</script>
