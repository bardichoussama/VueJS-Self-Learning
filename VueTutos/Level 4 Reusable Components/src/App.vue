<template>
  <div>
    <h1>Props Example</h1>
    <!-- Pass data to the child component -->
    <ChildComponent 
      message="Hello from Parent Component!" 
      username="John Doe" 
    />
  </div>
</template>

<script setup>
import ChildComponent from './components/ChildComponent.vue';
</script>
