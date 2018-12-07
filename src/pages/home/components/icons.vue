<template>
  <div class="icons">
		<swiper :options="swiperOption" v-if="showSwiper">
            <swiper-slide v-for="(page,index) in pages" :key="index">
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
    props:{
        list:Array
    },
    data() {
    	return{
			swiperOption:{
                 loop:true,
                 autoplay:false
               }
    	}
    },
    computed:{
    	pages (){
            const pages=[]
              this.list.forEach((item,index)=>{
            	const page=Math.floor(index/8)
            	if(!pages[page]){
                   pages[page]=[]
            	}
            	pages[page].push(item)
            })
            return pages
    	},
    	showSwiper(){
    		return this.list.length
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