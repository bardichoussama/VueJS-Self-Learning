<template>
  <div class="child">
    <!-- Use props in the template -->
    <p>{{ message }}</p>
    <p>Welcome, {{ username }}!</p>
  </div>
</template>

<script setup>
// Use `defineProps` to declare props in the Composition API
defineProps({
  message: {
    type: String,
    required: true, 
  },
  username: {
    type: String,
    required: true, 
  },
});
</script>
