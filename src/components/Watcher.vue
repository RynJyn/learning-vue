<template>
  <p>{{ count }}</p>
  <button type="button" v-on:click="count++">+</button>
  <button type="button" v-on:click="count--">-</button>
</template>

<script>
export default {
  name: 'WatcherComp',
  data() {
    return {
      count: 0
    }
  },
  watch: {
    count(curr, prev) {
      if (curr > 10 && curr > prev) {
        alert('Maximum number is 10')
        this.count = 0
      }

      if (curr < 0 && curr < prev) {
        alert('You must have a minimum of 0')
        this.count = 0
      }
    }
  }
}
</script>
