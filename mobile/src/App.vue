<template>
  <div id="app">
   <router-view v-if="isRouterAlive"></router-view>
	<Tabbar></Tabbar>
  </div>
</template>

<script>
	
	export default {
		name: 'app',
		components: {	
		},
		provide(){
			return{
				reload:this.reload
			}
		},
		data(){
			return{
				isRouterAlive:true
			}
		},
		methods:{
			reload(){
				this.isRouterAlive=false
				this.$nextTick(function(){
					this.isRouterAlive = true
				})
			}
		},
		created() {
	
	    },
	}
</script>
<style lang="less">

</style>
