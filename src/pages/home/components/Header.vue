<template>
	<div class="header">
		 <div class="header-left">
          <div class="iconfont back-icon">&#xe624;</div>
		 </div>
		 <div class="header-input">
		 	 <span class="iconfont input-icon">&#xe632;</span>
		 	 输入城市/景点/游玩主题
		 </div>
		 <router-link to="/city">
			 <div class="header-right">{{this.$store.state.city}}
	         <span class="iconfont arraw-icon">&#xe6aa;</span>
			 </div>
		</router-link>
	</div>
	
</template>


<script>
export default{
	name:'Header'
}	

</script>


<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
		.header {
			display:flex
			line-height:$headerHeight
			background:$bgColor
			color:#fff
		}
		.header-right
			color: #fff
			opacity:0.7
			font-weight:400
		.header-left{
		  	width: .64rem
            float: left
		  }
		  .back-icon{
		  	text-align: center
			font-size: .4rem
		  }
		  .header-input{
		  	flex: 1
			// width:100%
			height:.64rem
			line-height:.64rem
			margin-top:.12rem
			margin-left:.2rem
			background:#fff
			border-radius:.1rem
			color:#ccc
		  	padding-left:.3rem
		  } 
		  .input-icon{
		  	font-size:.26rem
		  	padding-right:.06rem
		  }
		  .header-right{
		  	width: 1.24rem
			float: right
			text-align: center
		  }
		  .arraw-icon{
		  	margin-left:-0.04rem
		  	font-size: .24rem
		  }
		 
		 	 		
		 	 		
		 	 		
		 
          
</style>