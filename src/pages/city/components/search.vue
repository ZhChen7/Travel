<template>
  <div>
    <div class="search">
      <input type="text" placeholder="输入城市名或拼音" class="search-input" v-model="keyword">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item" v-for="(item,key) in list" :key="key"
        @click="handleCityClick(item.name)"
        >{{item.name}}</li>
        <li class="search-item" v-show="hasNodata">没有找到匹配项</li>
      </ul>
    </div>
  </div>
</template>


<script>
import Bscroll from "better-scroll";
export default {
  name: "CitySearch",
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },
  computed: {
    hasNodata() {
      return !this.list.length;
    }
  },
  watch: {
    keyword() {
      // 节流
      if (this.timer) {
        clearInterval(this.timer);
      }
      if (!this.keyword) {
        this.list = [];
        return;
      }
      this.timer = setInterval(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value);
            }
          });
        }
        this.list = result;
      }, 100);
    }
  },
  methods:{
      handleCityClick(city){
           this.$store.commit('changeCity',city)
           this.$router.push('/')
      }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.search);
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  height: 0.72rem;
  padding: 0.1rem;
  background: $bgColor;
}

.search-input {
  width: 100%;
  height: 0.62rem;
  line-height: 0.62rem;
  text-align: center;
  border-radius: 0.2rem;
  margin-left: -0.05rem;
  color: #666;
}

.search-content {
  z-index: 1;
  overflow: hidden;
  position: absolute;
  top: 1.88rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #eee;
}

.search-item {
  line-height: 0.62rem;
  padding-left: 0.2rem;
  color: #666;
  background: #ffffff;
  border-bottom: 1px solid #eee;
}
</style>