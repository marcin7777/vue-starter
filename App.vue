<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>       
    <div v-if = "authenticatedUserName != ' '">    
    <h3>Jesteś zalogowany jako:  {{ authenticatedUserName }}</h3>  
    <a @click = logMeOut()>Wyloguj</a>
    </div>
     <div v-else>
    <input type= "text" v-model = "email">
    <button @click= "logMeIn()">Zaloguj</button>
    </div>
            
  </div>
</template>

<script>

export default {
 
	data() {
		  return {
		    email: '',
		    authenticatedUserName: ''
		  };
		  
		},
	
	methods: {
		logMeIn() {
			
		   this.authenticatedUserName = this.email;
		   
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
