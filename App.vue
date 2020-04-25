 GNU nano 4.6                                    App.vue
<template>
  <div id="app">
   <h1>Twój email to: {{email}}</h1>

   <div v-if="email.length < 10">Ale masz krótki adres!</div>
   <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
   <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

   <input type = "text" v-model="email">
   <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
  </div>

</template>

<script>


export default {
 data() {
 return {
<template>
  <div id="app">
   <h1>Twój email to: {{email}}</h1>

   <div v-if="email.length < 10">Ale masz krótki adres!</div>
   <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
   <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

   <input type = "text" v-model="email">
   <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
  </div>
   
</template>

<script>


export default {
 data() {
 return {

 title: 'Hello World',
 email: ''
 };
},
methods: {
  alertMyEmail() {
    alert(this.email);
  }
}
}
</script>

<style>

</style>

