<script setup>
import SignUpForm from '../components/SignUpForm.vue'
</script>

<template>
  <div class="signup">
    <SignUpForm />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .signup {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>
