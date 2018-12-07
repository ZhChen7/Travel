<template>
	<div>
<<<<<<< HEAD
		<home-header :city="city"></home-header>
		<home-swiper :list="SwiperList"></home-swiper>
		<home-icons  :list="iconList"></home-icons>
		<home-recommend :list="recommend"></home-recommend>
		<home-weekend :list="weekend"></home-weekend>
=======
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
		<home-recommend></home-recommend>
		<home-weekend></home-weekend>
>>>>>>> 0315c7856484394631d07fce92aaf1eb6a2c3402
	</div>
	
</template>


<script>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
<<<<<<< HEAD
import axios from 'axios'
=======

>>>>>>> 0315c7856484394631d07fce92aaf1eb6a2c3402
export default{
	name:'Home',
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecommend,
		HomeWeekend
<<<<<<< HEAD
	},
	data () {
		return {
           city: '',
           SwiperList:[],
           iconList:[],
           recommend:[],
           weekend:[]
		}
	},
	methods:{
		getHomeInfo(){
			axios.get('/api/index.json')
			  .then(this.getHomeInfoSucc)
		},
		getHomeInfoSucc(res){
			res = res.data
			if(res.ret && res.data){
				const data = res.data
                this.city = data.city
                this.SwiperList=data.swiperList
                this.iconList=data.iconList
                this.recommend=data.recommendList
                this.weekend=data.WeekendList
			}
		}
	},
	mounted(){
         this.getHomeInfo()
=======
>>>>>>> 0315c7856484394631d07fce92aaf1eb6a2c3402
	}
}	

</script>


<style>
	
</style>