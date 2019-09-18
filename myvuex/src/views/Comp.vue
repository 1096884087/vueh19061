<template>
	<ul>
		<li v-for="(a,index) in completed" :key="index">
			<input type="checkbox" v-model="a.comp"> 
			<span :class="{ 'isActive': a.comp }">{{a.value}}</span>
		</li>
	</ul>
</template>

<script>
	export default {
		data:function(){
			return {
				
			}
		},
		computed:{
			completed:function(){
				return this.$store.getters.completed
			}
		}
	}
</script>

<style>
	.isActive {
		text-decoration: line-through;
	}
	
</style>
