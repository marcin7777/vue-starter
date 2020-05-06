<template>
  <div>
    <label for="email">Zaloguj się e-mailem</label>
    <input v-bind:class="{ 'error-input': emailError }" id="email" type="email" v-model="email">
    <p class="error" v-if="emailError">Wpisz poprawny adres email</p>
    <button @click="enter()">{{ buttonLabel }}</button>
  </div>
</template>

<script>
  export default {
    props: ['buttonLabel'],
    data() {
      return {
        email: '',
      }
    },
    methods: {
      enter() {
        if(!this.emailError) {
          this.$emit('login', this.email);
        }
      }
    },
    mounted() {
      if (!this.buttonLabel) {
        this.buttonLabel = 'Zaloguj się';
      }
    },
    computed: {
      emailError: function() {
        return this.email.length < 3;
      }
    }
  }
</script>

<style>

</style>

