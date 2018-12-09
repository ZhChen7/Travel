<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item in hot" :key="item.id" 
             @click="handleCityClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) in cities" :key="key"
	    :ref="key">
        <div class="title">{{key}}</div>
        <div class="item-list">
          <div class="item" v-for="innerItem in item" :key="innerItem.id"
           @click="handleCityClick(innerItem.name)"
           >
            {{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
export default {
  name: "CityList",
  props: {
    hot: Array,
    cities: Object,
    letter:String
  },
  methods:{
      handleCityClick(city){
           this.$store.commit('changeCity',city)
           this.$router.push('/')
      }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  watch: {
    letter() {
        // console.log(this.letter)
      if (this.letter) {
		const element=this.$refs[this.letter][0]
		this.scroll.scrollToElement(element);
		// console.log(element)
      }
    }
  }
};
</script>


<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.title {
  line-height: 0.54rem;
  background: #eee;
  padding-left: 0.2rem;
  color: #666;
  border-top: 1px solid #ddd;
  font-size: 0.26rem;
}

.list {
  overflow: hidden;
  position: absolute;
  left: 0;
  right: 0;
  top: 1.78rem;
  bottom: 0;
  // background: red
}

.button-list {
  overflow: hidden;
  padding: 0.1rem 0.6rem 0.1rem 0.1rem;
}

.button-wrapper {
  width: 33.33%;
  float: left;
}

.button {
  margin: 0.1rem;
  text-align: center;
  border: 0.02rem solid #ccc;
  padding: 0.1rem 0;
  border-radius: 0.08rem;
}

.item-list {
  padding-left: 0.2rem;
  line-height: 0.76rem;
}

.item {
  border-bottom: 1px solid #eee;
}
</style>