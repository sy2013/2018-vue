<template>
  <div class="header">
  	<div class="back iconfont" @click="handleBackClick">
  		&#xe667;
  	</div>    
                   城市选择     	     
   </div>  
</template>

<script>
	export default{
		name:'city-header',
		methods:{
			handleBackClick() {
				this.$router.go(-1)
			}
		}
	}
</script>

<style lang='stylus' scoped>
@import '../../assets/styles/common/varibles.styl'
   .header
      position:relative
      height:44px
      line-height:44px
      text-align:center
      background:$bgColor
      color:#fff 
      .back
          position:absolute
          width:58px
          line-height:44px
          text-align:center
          font-size:22px
      
        
        
</style>