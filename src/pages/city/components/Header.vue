<template>
	 <div class="header">
	 城市选择
    <div class="iconfont header-back">&#xe624;</div>

	</div>

</template>


<script>
export default{
	name:'CityHeader'
}


</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
   .header
   	   position: relative
       overflow: hidden
       height: $headerHeight
       line-height: $headerHeight
       text-align: center
       color: #fff
       background: $bgColor
       font-size: .32rem
      .header-back
      	position: absolute
      	left: .1rem
      	top: 0
      	width: .64rem
      	text-align: center
      	font-size: .4rem
</style>