<template>
  <div class="main">
     <city-header></city-header>
     <city-search></city-search>
     <city-list class="list" :lists="lists" :hotcity="hotcity"></city-list>
   </div>  
</template>

<script>
	import CityHeader from './header'
	import CitySearch from './search'
	import CityList from './list'
	import axios from 'axios'
	
	export default{
		name:'city',
		components: {
			CityHeader,
			CitySearch,
			CityList
		},
		data() {
			 return{
			 	  lists:[],
			 	  hotcity:[]
			 }
		},
		methods: {
			getListInfo() {
				 axios.get( '/api/city.json' )
				   .then( this.handleListDateSucc.bind(this) )
				   .catch( this.handleListDateErr.bind(this) )
			},
			handleListDateSucc(res) {
				res = res ? res.data : null
				if( res && res.ret && res.data){
					this.lists = res.data.city
					this.hotcity = res.data.hotcity
				}else{
					 this.handleListDateErr()
				}
			},
			handleListDateErr(){
				console.log('获取数据失败')
			}
		},
		created() {
			this.getListInfo()
		}
	}
</script>

<style lang='stylus' scoped>
  .main
     display:flex
     flex-direction:column
     position:absolute
     top:0
     left:0
     right:0
     bottom:0
     .list
        flex:1
     
</style>