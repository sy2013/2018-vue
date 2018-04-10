<template>
    <div class="header">
        <div class="back iconfont">&#xe667;</div>
        <div class="search">
            <span class="search-content iconfont">&#xe60c;</span>
                                请输入搜素内容
        </div>
        <router-link :to="{ name:'city' }">       	
	        <div class="city">
	            {{city}}
	            <span class='city-down iconfont'>&#xe629;</span>                      
	        </div>
        </router-link>
    </div>
</template>

<script>
	import { mapState } from 'vuex'
export default {
  name: 'index-header',
  computed: {
  	...mapState(['city'])
  }
}
</script>

<style lang='stylus' scoped>
@import '../../assets/styles/common/varibles.styl'
   .header
       display:flex
       height:44px
       background:$bgColor
       color:#fff 
       .back
          width:58px
          line-height:44px
          text-align:center
          font-size:22px
        .search
           flex:1
           position:relative
           height:30px
           margin-top:7px
           line-height:30px
           text-indent:10px
           background:#fff
           border-radius:3px
           font-size:15px
           color:#919191 
           .search-content
              position:relative
              top:1px
              font-size:20px 
        .city
          float:right
          padding:0 10px 
          line-height:44px
          color:#fff
          .city-down
             font-size:16px      
</style>
