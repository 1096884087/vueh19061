<template>
  <div class="about">
    <ul>
    	<li v-for="(a,index) in active"  :key="a.count">
    		<input type="checkbox" v-model="a.comp">
			<span :class="{ 'isActive': a.comp }">{{a.value}}</span>
    	</li>
    </ul>
  </div>
</template>

<script>
	export default {
		data:function(){
			return {
				
			}
		},
		computed:{
			active:function(){
				console.log(this.$store.getters.active)
				return this.$store.getters.active
			}
		}
	}
</script>
