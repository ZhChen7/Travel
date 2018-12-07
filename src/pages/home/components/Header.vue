<template>
	<div class="header">
		 <div class="header-left">
          <div class="iconfont back-icon">&#xe624;</div>
		 </div>
		 <div class="header-input">
		 	 <span class="iconfont input-icon">&#xe632;</span>
		 	 输入城市/景点/游玩主题
		 </div>
		 <div class="header-right">{{this.city}}
          <span class="iconfont arraw-icon">&#xe6aa;</span>
		 </div>
	</div>
	
</template>


<script>
export default{
	name:'Header',
	props: {
		city: String
	}
}	

</script>


<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
		.header {
			display:flex
			line-height:.86rem
			background:$bgColor
			color:#fff
		}
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
		  	padding-left:.2rem
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