<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo.png">
		<ul>
			<li v-for="item in users">
			   {{item.id}} : {{item.name}}
			</li>
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
			axios.get('http://47.95.247.123:3000/api/users').then(res=>{
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
