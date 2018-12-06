<template>
	<div>
	<div class="recommend-title">热销推荐</div>
	<ul>
		<li class="item"  v-for="item in recommendList" :key="item.id">
			<div class="item-img-wrapper">
				 <img class="item-img" :src="item.imgUrl" >
			</div>
			<div class="item-info">
				<p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">查看详情</button>
			</div>
		</li>
	</ul>

	</div>
	
     
</template>

<script>
export default{
     name:'HomeRecommend',
     data () {
     	return{
     		 recommendList:[{
            	id:'0001',
            	imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
            	title:'故宫',
            	desc:'北京故宫是中国明清两代的皇家宫殿，是中国古代宫廷建筑之精华。'
            },{
            	id:'0002',
            	imgUrl:'http://img1.qunarzz.com/sight/p0/1711/53/53f7752ece875d00a3.img.jpg_200x200_5c006913.jpg',
            	title:'龙脉温泉',
            	desc:'龙脉温泉隶属于北京龙脉温泉疗养院，位于昌平区小汤山镇，地处故宫中轴线。距市区20公里，近邻长城、十三陵、蟒山、银山塔林、雪世界等景区，交通便利。集住宿、餐饮、娱...'
            },{
            	id:'0003',
            	imgUrl:'https://p1.meituan.net/200.0/hotel/75e4d6f1d7d610b1d87fb0e5c0ef9d602381382.jpg.webp',
            	title:'罗田三里畈温泉',
            	desc:'罗田三里畈温泉官网主要提供湖北省黄冈市罗田三里畈温泉景区旅游指南，包括罗田三里畈温泉门票、罗田三里畈温泉度假区攻略、罗田三里畈温泉旅游线路、交通概况、景点咨询..。'
            }]
     	}
           
     }
}	

</script>


<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title
	margin-top: .2rem
	line-height: .8rem
	background: #eee
	text-indent: .2rem
.item
	overflow: hidden
	display: flex
	height: 1.9rem
	// background: red
	border-bottom: 1px solid #eee
.item-img
	height: 1.7rem
	width: 1.7rem
	padding: .1rem
.item-info
	flex: 1
	padding :.1rem
	min-width: 0
.item-title
	line-height: .54rem
	font-size: .32rem
	ellipsis()
.item-desc
	line-height: .4rem
	color: #aaa
	ellipsis()
.item-button
	line-height:.44rem
	margin-top: .1rem
	background: #ff9300
	padding: 0 .2rem
	border-radius: .06rem
	opacity:.8
</style>