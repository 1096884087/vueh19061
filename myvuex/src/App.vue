<template>
  <div id="app">
	<input class="myinput" type="text" v-model="todo" placeholder="请输入待办事项"  v-on:keyup.enter="addTodo">
    <div id="nav">
      <router-link to="/">all</router-link> |
      <router-link to="/about">active</router-link>|
	  <router-link to="/comp">completed</router-link>
    </div>
    <router-view/>
	<p>待办事项还有{{num}}项</p>
  </div>
</template>

<script>
	export default {
		data:function(){
			return {
				todo:""
			}
		},
		computed:{
			num:function(){
				return this.$store.getters.active.length
			}
		},
		methods:{
			addTodo:function(){
				this.$store.commit('increment',{value:this.todo,comp:false})
				this.todo=""
			}
		}
	}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.myinput {
	width: 300px;
	height: 40px;
	background-color: #ccc;
	padding-left: 10px;
	margin-top: 40px;
}
</style>
