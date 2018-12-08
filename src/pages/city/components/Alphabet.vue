<template>
	<ul class="list">
		<li class="item" v-for="(item,key) in list" :key="key">{{key}}</li>
	</ul>

</template>

<script>
export default{
	name:'CityAlphabet',
	props: {
    list: Object
  }
}	

</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
	display: flex
	flex-direction: column
	justify-content: center
	position: absolute
	top: 0.6rem
	right: 0
	bottom: 0
	width: .4rem
	// background: red
.item
	line-height: .4rem
	text-align: center
	color: $bgColor

</style>