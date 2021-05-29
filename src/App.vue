<template>
  <div>
	<h1>Witaj w systemie do zapisów na zajęcia</h1>
	<div v-if="authenticatedEmail !=''">
		<h4> Jesteś zalogowany jako {{ authenticatedEmail }} </h4>
		<a @click="logMeOut()">Wyloguj</a>
	</div>
	<div v-else>
		<login-form @login="logMeIn($event)" button-label="Wchodzę"></login-form>
		<login-form @login="logMeIn($event)" :button-label="'Wleć ' + (2+2)"></login-form>
		<login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
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
			authenticatedEmail: ''
		};
	},	
	
	methods: {
		logMeIn(username){
			this.authenticatedEmail = username;
		},
		logMeOut(){
			this.authenticatedEmail = '';
		}
	}
};
</script>

<style>
	
	
</style>
