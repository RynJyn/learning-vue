<script setup>
import MyComponent from '../components/MyComponent.vue'
import InputTesting from '../components/InputTesting.vue'
import ConditionalRendering from '../components/ConditionalRendering.vue'
import ForLoop from '../components/ForLoop.vue'
import SignUpForm from '../components/SignUpForm.vue'
import WatcherComp from '../components/Watcher.vue'
import DynComps from '../components/DynamicComponents.vue'
</script>

<template>
  <h1>Components from Course</h1>
  <span>(most of them, anyway)</span>

  <MyComponent />
  <InputTesting />
  <ConditionalRendering />
  <ForLoop />
  <SignUpForm />
  <DynComps />

  <teleport to="#teleport">
    <WatcherComp />
  </teleport>
</template>
