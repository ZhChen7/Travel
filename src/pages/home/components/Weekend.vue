<template>
	<div>
	<div class="recommend-title">周末去哪</div>
	<ul>
		<li class="item"  v-for="item in recommendList" :key="item.id">
			<div class="item-img-wrapper">
				 <img class="item-img" :src="item.imgUrl" >
			</div>
			<div class="item-info">
				<p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
			</div>
		</li>
	</ul>

	</div>
	
     
</template>

<script>
export default{
     name:'HomeWeekend',
     data () {
     	return{
     		 recommendList:[{
            	id:'0001',
            	imgUrl:'https://imgs.qunarzz.com/p/p32/1409/28/9b94d65a5ee55feffffffffc8d65eac.jpg_750x500_034da3b0.jpg',
            	title:'武汉欢乐谷',
            	desc:'武汉欢乐谷占地约35万平方米，2012年4月29日开园迎宾，其由梦想大道、卡通工厂、欢乐时光、极速世'
            },{
            	id:'0002',
            	imgUrl:'https://imgs.qunarzz.com/p/p32/1409/28/9b94d65a5ee55feffffffffc8d65eac.jpg_750x500_034da3b0.jpg',
            	title:'武汉欢乐谷',
            	desc:'武汉欢乐谷占地约35万平方米，2012年4月29日开园迎宾，其由梦想大道、卡通工厂、欢乐时光、极速世'
            },{
            	id:'0003',
            	imgUrl:'https://imgs.qunarzz.com/p/p32/1409/28/9b94d65a5ee55feffffffffc8d65eac.jpg_750x500_034da3b0.jpg',
            	title:'武汉欢乐谷',
            	desc:'武汉欢乐谷占地约35万平方米，2012年4月29日开园迎宾，其由梦想大道、卡通工厂、欢乐时光、极速世'
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
.item-img-wrapper
	overflow: hidden
	height: 0
	padding-bottom: 33.9%
.item-img
	width: 100%
.item-info
	padding :.1rem
.item-title
	line-height: .54rem
	font-size: .32rem
	ellipsis()
.item-desc
	line-height: .4rem
	color: #aaa
	ellipsis()
</style>