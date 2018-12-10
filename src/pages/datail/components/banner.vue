<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <div class="iconfont">&#xe631; 39</div>
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="gallaryImgs" v-show="showGallary" @close="handleBannerClose"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import commonGallary from "common/gallary/Gallary";
import FadeAnimation from "common/fade/FadeAnimation";
export default {
  name: "DetailBanner",
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data() {
    return {
      showGallary: false
    };
  },
  components: {
    commonGallary,
    FadeAnimation
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true;
    },
    handleBannerClose() {
      this.showGallary = false;
    }
  }
};
</script>

<style lang="stylus" scoped>
.banner {
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
  position: relative;
}

.banner-img {
  width: 100%;
}

.banner-info {
  display: flex;
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  line-height: 0.6rem;
  color: #fff;
  background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
}

.banner-title {
  flex: 1;
  font-size: 0.32rem;
  padding: 0.2rem;
}

.banner-number {
  padding: 0 0.4rem;
  height: 0.32rem;
  border-radius: 0.2rem;
  line-height: 0.32rem;
  background: rgba(0, 0, 0, 0.8);
  font-size: 0.24rem;
  margin: 0.35rem 0.3rem;
}

.banner-icon {
  font-size: 0.24rem;
}
</style>

