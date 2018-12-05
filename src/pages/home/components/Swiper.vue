<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide v-for="item in swiperList" :key="item.id">
	    	<img  class="swipe-img" :src="item.imgUrl">
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	    <!-- <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
	  </swiper>
	</div>
 
</template>

<script>
export default{
	name:'HomeSwiper',
	data (){
		return{
			swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
			},
			swiperList:[{
				id:'0001',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/6c/b1b8677dc1886d02.jpg_750x200_1931f6c4.jpg'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/piao/fusion/1811/29/2a6b77b6ff72402.jpg_750x200_d4cec568.jpg'
			}]
		}
	}
}

</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
	background:#fff
.wrapper
	 overflow: hidden
	 width: 100%
	 height: 0
	 padding-bottom : 31.25%
	 background: #eee
.swipe-img
	  width: 100%

</style>