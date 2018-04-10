<template>
	<div class='icons'>
		<swiper :options="swiperOption">
		    <swiper-slide class="area-con" v-for="(page,index) in pageList" :key="index">
		    		<div class="area-item" v-for="item in page" :key="item.id">
		    			<img :src="item.imgUrl" alt="" class="area-item-img"/>
		    			<p class="area-item-title">{{item.title}}</p>
		    		</div>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>

<script>
	export default {
		name: 'index-icons',
		props:{
			list:Array
		},
		data() {
		  	return {
		  		swiperOption:{
		  			pagination:'.swiper-pagination'
		  		}  		
  	         }      
       },
       computed: {
       	  pageList() {
       	  		const pages = []
       	  		this.list.forEach( ( value, index ) => {
       	  			 const page = Math.floor( index/8 )
       	  			 if( !pages[page] ){
       	  			 	pages[page] = []
       	  			 }
       	  			 pages[page].push(value)
       	  		})
       	  		return pages
       	  }
       }
	}
</script>

<style lang='stylus' scoped>
  .icons
    width:100%
    overflow:hidden
    height: 190px
    .area-con
        display:flex
        flex-wrap: wrap
        padding-top:15px
        .area-item
           width:25%
           height:90px
           padding-top: .3rem
           text-align: center
           .area-item-img
              width:40px
              height:40px
           .area-item-title
                overflow:hidden
                white-space:nowrap
                text-overflow:ellipsis
                margin-top: 3px
                font-size: 14px
			    color: #212121
</style>