<template>
  <h3 v-if="display">Conditional Rendering</h3>
  <h3 v-else>Else</h3>
  <button v-on:click="display = !display">Click Here</button>
</template>

<script>
export default {
  name: 'ConditionalRendering',
  data() {
    return {
      display: true
    }
  }
}
</script>
