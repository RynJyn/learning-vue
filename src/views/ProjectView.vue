<script setup>
import ProjectSignUp from '../components/final_project/SignUpForm.vue'
import ProjectProfile from '../components/final_project/ProjectProfile.vue'
</script>

<template>
  <h1>Final Project</h1>
  <h2>Finishing up the course with an API project</h2>
  <!--<ProjectSignUp />-->
  <component :is="active" />
</template>

<script>
export default {
  data() {
    return {
      active: 'ProjectSignUp'
    }
  },
  components: { ProjectSignUp, ProjectProfile },
  beforeMount() {
    const isSignedUp = localStorage.getItem('user-info')
    if (isSignedUp) {
      this.active = 'ProjectProfile'
    }
  }
}
</script>
