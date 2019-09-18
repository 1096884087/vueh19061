<template>
  <div class="home">
    <ul>
    	<li v-for="(a,index) in allTodo" :key="index" >
			<input type="checkbox" v-model="a.comp">
			<span :class="{ 'isActive': a.comp }">{{a.value}}</span>
		</li>
    </ul>
  </div>
</template>

<script>
export default {
	 computed:{
		 allTodo:function(){
			 return this.$store.state.todos
		 }
	 }
}
</script>

<style>
	.isActive {
		text-decoration: line-through;
	}
	
	.home {
		text-align: left;
	}
</style>
