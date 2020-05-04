<template>
  <div>
    <h1>System do zapisów na zajęcia</h1>       
    <div v-if = "authenticatedUserName != ' '">    
    <h3>Witaj {{ authenticatedUserName }} !</h3> 
    <a @click = logMeOut()>Wyloguj</a> 
     <meetings-page>   </meetings-page> 
    </div>
     <div v-else>
    <login-form @login="logMeIn($event)" ></login-form>             
    </div>  
            
  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";
import MeetingsPage from "./MeetingsPage";


export default { 

	components: {LoginForm, MeetingsPage},
	data() {
		  return {		    
		    authenticatedUserName: ''
		  };		  
		},
	
	methods: {
		logMeIn(username) {
			if (username != "") {
				this.authenticatedUserName = username;}
			else {
				alert("Wpisz swój e-mail!");
			}
		  
		   
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
