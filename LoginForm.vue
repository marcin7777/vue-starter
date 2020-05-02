<template>
   <div>
       <label>Zaloguj się e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">Wchodzę</button>
   </div>
</template>

<script>
export default {
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 },


computed:
 {   buttonLabelToDisplay() {   
  return this.buttonLabel || 'Zaloguj się';  
     } 
  }

</script>
