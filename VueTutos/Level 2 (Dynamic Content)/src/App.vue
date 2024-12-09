<script setup>
import  {  reactive,computed }from 'vue'

const user = reactive({
  firstname :"",
  lastname : ""
});

const fullName = computed(()=>{
  return ` ${user.firstname} ${user.lastname}`
})


</script>

<template>
  <div>
    <h1>Basic Data Binding</h1>
    <div>
      <label for="firstname">First Name :</label>
      <input type="text" v-model="user.firstname">
    </div>
    <div>
      <label for="lastname">Last Name :</label>
      <input type="text" v-model="user.lastname">
    </div>
    <div>
      <p v-if="fullName.trim().length > 0">
        Hello {{ fullName }}
      </p>
      <p v-else class="text-green-500"> not data yet</p>

    </div>
  </div>
</template>