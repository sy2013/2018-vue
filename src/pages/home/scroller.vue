<template>
	<div ref="scroller" class="scroller">	  
		<ul class="content">
		    <li v-for="item in list" :key="item.id" class="content-list">
		    	<img :src="item.imgUrl" alt="" class="content-img"/>
		    	<p class="title">{{item.title}}</p>
		    </li>
		</ul>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	export default{
		name: 'index-scroller',
		props:{
			list:Array
		},
		watch: {
			list () {
				this.$nextTick( () => {					
					this.scroller.refresh()	
				})
			}
		},
		mounted() {
			this.scroller = new BScroll( this.$refs.scroller )
		}
	}
</script>

<style lang="stylus" scoped>
   
       .content-list
          display:flex
        .content-img
            width:100px
            height:100px
         
</style>