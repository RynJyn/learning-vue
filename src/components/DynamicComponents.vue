<script setup>
import FirstComp from './dynamic/first.vue'
import SecondComp from './dynamic/second.vue'
import ThirdComp from './dynamic/third.vue'
</script>

<template>
  <h2>Dynamic Components:</h2>
  <button v-on:click="active = 'FirstComp'">First</button>
  <button v-on:click="active = 'SecondComp'">Second</button>
  <button v-on:click="active = ThirdComp">Third</button>
  <component :is="active" />
</template>

<script>
export default {
  name: 'DynComps',
  components: { FirstComp, SecondComp, ThirdComp },
  data() {
    return {
      active: 'FirstComp'
    }
  }
}
</script>
