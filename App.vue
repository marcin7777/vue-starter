<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>       
    <div v-if = "authenticatedUserName != ' '">    
    <h3>Jesteś zalogowany jako:  {{ authenticatedUserName }}</h3>  
    <a @click = logMeOut()>Wyloguj</a>
    </div>
     <div v-else>
    <login-form @login="logMeIn($event)"
    button-label="Zaloguj się"></login-form>
    <login-form @login="logMeIn($event)" 
    button-label="Wejdź"></login-form>
    <login-form @login="logMeIn($event)" 
    button-label="Wleć"></login-form>
    <login-form @login="logMeIn($event)"
     :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    </div>            
  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";

export default { 
	components: {LoginForm},
	data() {
		  return {		    
		    authenticatedUserName: ''
		  };		  
		},
	
	methods: {
		logMeIn(username) {
			
		   this.authenticatedUserName = username;		   
		  },
		logMeOut() {
			  this.authenticatedUserName = ' ';
			  this.email ='';
		}
		  
	}
	
}
</script>

<style>

</style>
