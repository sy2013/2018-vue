<template>
   <div>
       <index-header></index-header>
       <index-swiper :list='swiper'></index-swiper>
   </div>
</template>

<script>
	import IndexHeader from './header'
	import IndexSwiper from './swiper'
	import axios from 'axios'
export default {
  name: 'index',
  components: {
  	IndexHeader,
  	IndexSwiper
  },
  data() {
  	return {
  		swiper:[]
  	}
  },
  methods: {
  	 getIndexData() {
  	 	axios.get('/api/index.json')
  	 	  .then( this.handleGetDataSucc.bind(this) )
  	 	  .catch( this.handleGetDataErr.bind(this) )
  	 },
  	 handleGetDataSucc(res) {
        const data = res.data.data
        this.swiper = data.swiper
  	 },
  	 handleGetDataErr(res) {
  	 	
  	 }
  },
  created() {
  	this.getIndexData()
  }
  
}
</script>

<style>

</style>
