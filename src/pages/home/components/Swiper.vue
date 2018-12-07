<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showSwiper">
	    <!-- slides -->
	    <swiper-slide v-for="item in list" :key="item.id">
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
	props: {
		list: Array
	},
	data (){
		return{
			 swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
			}
		}
	},
	computed:{
		showSwiper(){
			return this.list.length
		}
	}
}

</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
	background:#fff
.wrapper
	 overflow: 	
	 width: 100%
	 height: 0
	 padding-bottom : 27%
	 background: #eee
.swipe-img
	  width: 100%

</style>