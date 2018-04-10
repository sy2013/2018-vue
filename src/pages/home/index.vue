<template>
	
	   <div class="main">
	       <index-header></index-header>
	       <index-swiper :list='swiper'></index-swiper>
	       <index-icons :list='icons'></index-icons>
	       <index-scroller :list = "sights"></index-scroller>						
	   </div>
	
</template>

<script>
	import IndexHeader from './header'
	import IndexSwiper from './swiper'
	import IndexIcons from './icons'
	import IndexScroller from './scroller'
	import { mapState,mapMutations } from 'vuex'
	import axios from 'axios'
	
export default {
  name: 'index',
  components: {
  	IndexHeader,
  	IndexSwiper,
  	IndexIcons,
  	IndexScroller
  },
  data() {
  	return {
  		swiper:[],
  		icons:[],
		sights:[]
  	}
  },
  computed: {
  	...mapState(['city'])
  },
  methods: {
  	...mapMutations(['changeCity']),
  	 getIndexData() {
  	 	axios.get('/api/index.json?city=' + this.city)
  	 	  .then( this.handleGetDataSucc.bind(this) )
  	 	  .catch( this.handleGetDataErr.bind(this) )
  	 },
  	 handleGetDataSucc(res) {
        const data = res.data.data
        this.changeCity( data.city )
        this.swiper = data.swiper
        this.icons = data.icons
        this.sights = data.sights
  	 },
  	 handleGetDataErr(res) {
  	 	
  	 }
  },
  created() {
  	this.getIndexData()
  }
  
}
</script>

<style lang='stylus' scoped>
</style>
