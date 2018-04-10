<template>
  <div class="list">
	  <div class="area">
	     <div class="title">当前位置</div>
	     <div class="content">
	        <div class="button">
	        	<div class='button-con button-active'>{{<!--city ||--> '北京'}}</div>
	        </div>
	     </div>
	  </div>
	  <div class="area">
	     <div class="title">热门城市</div>
	     <div class="content">
	        <div class="button" v-for="item in hotcity" :key="item.id">
	        	<div class='button-con'>{{item.city}}</div>
	        </div>
	     </div>
	  </div>
  </div>
</template>

<script>
export default {
  name: 'city-list',
  props:{
  	lists:Array,
  	hotcity:Array
  },
  watch: {
  	hotcity() {
  		console.log(this.hotcity)
  	}
  }

}
</script>

<style lang='stylus' scoped>
@import '../../assets/styles/common/varibles.styl'
.area 
   .title
      line-height:28px
      padding-left:25px
      background:#eee
      color:#616161
      font-size:16px
  .content
     overflow:hidden
     text-align:center
     .button
        float:left           
        width:33.33%
       .button-con
         position:relative
         margin:16px
         padding:3px
         border:1px solid #ccc
         text-align:center
         color:#666
       .button-active
           color:$bgColor
           border-color:$bgColor   		
</style>
