<template>
  <div class="icons">
		<swiper :options="swiperOption" >
            <swiper-slide v-for="(page,index) in pages":key="index">
				<div class="icon" v-for="item in page" :key="item.id" >
					 <div class="icon-img">
					  <img class="icon-imgcontent" :src="item.imgUrl" >
					 </div>
					  <p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
       </swiper>
 	 </div>
  </div>
</template>

<script>
export default{
    name:'HomeIcons',
    data(){
    	return{
			  swiperOption:{
              pagination:'.swiper-  ',
              loop:true
			},
    		iconList:[{
    			id:'0001',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
    			desc:'景点门票'
    		},{
    			id:'0002',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png',
    			desc:'当地好玩'
    		},{
    			id:'0003',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
    			desc:'自然风光'
    		},{
    			id:'0004',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1811/5e/c640ec3b7d7ae802.png',
    			desc:'打卡圣地'
    		},{
    			id:'0005',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
    			desc:'全部娱乐'
    		},{
    			id:'0006',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1811/5e/c640ec3b7d7ae802.png',
    			desc:'打卡圣地'
    		},{
    			id:'0007',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png',
    			desc:'当地好玩'
    		},{
    			id:'0008',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
    			desc:'景点门票'
    		},{
    			id:'0009',
    			imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
    			desc:'自然风光'
    		},]
    	}
    },
    computed:{
    	pages (){
            const pages=[]
            this.iconList.forEach((item,index)=>{
            	const page=Math.floor(index/8)
            	if(!pages[page]){
                   pages[page]=[]
            	}
            	pages[page].push(item)
            })
            return pages
    	}
    }
}	

</script>

<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
   @import '~styles/mixins.styl'
.icons >>> .swiper-container
	// overflow: hidden
	height: 0
	padding-bottom: 50%
	// padding-bottom: 100%
	// background: green
.icons
    margin-top: .2rem   
.icon
	position: relative
	overflow: hidden
	float:left
	width:25%
	height: 0
	padding-bottom: 25%
	// background: red
	text-align:center
.icon-img
	position: absolute
	top:0
	left:0
	right:0
	bottom : .44rem
.icon-imgcontent{
	display:block 
	margin: 0 auto
	height: 100%
}
.icon-desc
	position:absolute
	bottom:0rem
	left:0
	right:0
	color:$darkTextColor
	line-height:.44rem
	height: .44rem
	text-align:center
	font-size: .16rem
	font-family: Arial,"Microsoft Yahei","Helvetica Neue",Helvetica,sans-serif
	overflow: hidden
	ellipsis()
</style>