<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo.png">
		<ul>
			<li v-for="item in users">{{item.name}}</li>
		</ul>
	</div>
</template>

<script>
	import axios from 'axios'
	export default {
		name: 'app',
		data(){
			return{
				users:[]
			}
		},
		mounted(){
			axios.get('http://120.27.3.92/api/users').then(res=>{
				 this.users = res.data;
				 
			})
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
