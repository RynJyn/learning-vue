<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()
</script>

<template>
  <div class="profile">
    <h1>Profile</h1>
    <p>ID: {{ route.params.id }}</p>
  </div>
</template>
