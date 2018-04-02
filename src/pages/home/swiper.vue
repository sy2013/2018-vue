<template>
    <div>
       <swiper :options="swiperOption">
    <!-- slides -->
		    <swiper-slide v-for='item in list' :key="item.id" class="swiper-slide-content">
		    	<img :src="item.imgUrl" alt="" class="swiper-img"/>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
    </div>
</template>

<script>
	
export default {
  name: 'index-swiper',
  props:{
  	list:Array
  },
  data() {
  	return {
  		swiperOption:{
			loop:true,
			autoplay: 1000,
			loop: true,
			observer:true,
			observeParents:true,
			slidesPerView : 'auto',
			loopedSlides :20,
			autoplayDisableOnInteraction :false,
  			pagination:'.swiper-pagination',
  			paginationClickable :true
  		}  		
  	}
  }
}
</script>

<style lang='stylus' scoped>
      .swiper-pagination >>> .swiper-pagination-bullet-active
         background:#fff
      .swiper-slide-content
          overflow:hidden
          height:0
          padding-bottom:31.25%
          .swiper-img
             width:100%
</style>
