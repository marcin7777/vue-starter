<template>
   <div>
       <label>Zaloguj się e-mailem</label>
       <input type="email" v-model="email">
<<<<<<< HEAD
       <button @click="enter()">{{buttonLabelToDisplay}}</button>
   </div>
</template>


<script>
export default {
	props: ['buttonLabel'],
=======
       <button @click="enter()">Wchodzę</button>
   </div>
</template>

<script>
export default {
>>>>>>> e46985cdfa508f72f560b6f845c38308bbb1bbaa
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

<<<<<<< HEAD
/* mounted() {
  if (!this.buttonLabel) {
    this.buttonLabel = 'Zaloguj się';
  }
}, */
=======

>>>>>>> e46985cdfa508f72f560b6f845c38308bbb1bbaa
computed:
 {   buttonLabelToDisplay() {   
  return this.buttonLabel || 'Zaloguj się';  
     } 
  }

<<<<<<< HEAD
}
=======
>>>>>>> e46985cdfa508f72f560b6f845c38308bbb1bbaa
</script>
