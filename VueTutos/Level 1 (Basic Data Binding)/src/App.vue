<script setup>
import  { ref }from 'vue'

const firstname = ref('')
const lastname = ref('')
</script>

<template>
  <div>
    <h1>Basic Data Binding</h1>
    <div>
      <label for="firstname">First Name :</label>
      <input type="text" v-model="firstname">
    </div>
    <div>
      <label for="lastname">Last Name :</label>
      <input type="text" v-model="lastname">
    </div>
    <div>
      <p v-if="firstname && lastname">
        Hello {{ firstname  }} , {{ lastname }}
      </p>
      <p v-else class="text-green-500"> not data yet</p>

    </div>
  </div>
</template>