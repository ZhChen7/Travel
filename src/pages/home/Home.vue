<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
	</div>
	
</template>


<script>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'

export default{
	name:'Home',
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons
	}
}	

</script>


<style>
	
</style>