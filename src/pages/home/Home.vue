<template>
	<div>
		<home-header :city="city"></home-header>
		<home-swiper :list="SwiperList"></home-swiper>
		<home-icons  :list="iconList"></home-icons>
		<home-recommend :list="recommend"></home-recommend>
		<home-weekend :list="weekend"></home-weekend>
	</div>
	
</template>


<script>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default{
	name:'Home',
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecommend,
		HomeWeekend
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
	}
}	

</script>


<style>
	
</style>