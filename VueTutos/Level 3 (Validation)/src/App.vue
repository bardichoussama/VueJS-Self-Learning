<script setup>
import  {  reactive,computed }from 'vue'

const user = reactive({
  firstname : "",
  lastname : ""
});

const errors = reactive({
  firstname : null,
  lastname : null
})

const fullName = computed(()=>{
  return `${user.firstname} ${user.lastname}`.trim()
})

const validateFirstName = ()=>{
  if(!user.firstname){
    errors.firstname = "First name is required.";
  }
  else{
    errors.firstname = null;
  }
}
const validateLastName = ()=>{
 errors.lastname = !user.lastname ?  "First name is required." : null
}
const isFormValid = computed(() => {
      return  !errors.firstname && !errors.lastname && user.firstname && user.lastname
    });

</script>

<template>
  <div>
    <h1>Validation</h1>
    <div>
      <label for="firstname">First Name :</label>
      <input type="text" v-model="user.firstname" @input="validateFirstName">
      <p v-if="errors.firstname" class="text-red-500 text-sm" > {{ errors.firstname }}</p>
    </div>
    <div>
      <label for="lastname">Last Name :</label>
      <input type="text" v-model="user.lastname" @input="validateLastName">
      <p v-if="errors.lastname" class="text-red-500 text-sm" > {{ errors.lastname }}</p>
    </div>
    <div>
      <p v-if="isFormValid">
        Hello {{ fullName }}
      </p>
      <p v-else class="text-gray-500">Please correct the errors above.</p>

    </div>
  </div>
</template>