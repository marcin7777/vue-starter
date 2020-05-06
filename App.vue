<template>
  <div>
    <h1>System do zapisów na zajęcia</h1>       
    <div v-if = "authenticatedUserName != ' '">    
    <h3>Witaj {{ authenticatedUserName }} ! 
    <button @click = logMeOut()>Wyloguj</button><h3>
    <hr> 
     <meeting-page> :user="authenticatedUserName"/> 
    </div>
     <div v-else>
    <login-form @login="logMeIn($event)" ></login-form>             
    </div>  
            
  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";
import MeetingsPage from "./MeetingPage";


export default { 

	components: {LoginForm, MeetingPage},
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
