<template>
  <div class='search'>
	  <input class="search-input" type="text" placeholder="输入城市名或者拼音"/>
  </div>
</template>

<script>
export default {
  name: 'city-search'

}
</script>

<style lang="stylus" scoped>
@import '../../assets/styles/common/varibles.styl'
.search
   height:36px
   padding:0 20px 
   background:$bgColor
   .search-input
      line-height:30px
      height:30px
      margin-top:3px
      padding:0 10px
      width:100%
      outline:none
      border-radius:3px
      border:0
      text-align:center
      font-size:15px
      color:#666
      box-sizing:border-box
</style>
