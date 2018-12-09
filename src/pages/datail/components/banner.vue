<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img
        class="banner-img"
        src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg"
      >
      <div class="banner-info">
        <div class="banner-title">故宫(AAAAA景区)</div>
        <div class="banner-number">
          <div class="iconfont">&#xe631; 39</div>
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" 
    @close="handleBannerClose"
    ></common-gallary>
  </div>
</template>

<script>
import commonGallary from "common/gallary/Gallary";
export default {
  name: "DetailBanner",
  data() {
    return {
      showGallary: false,
      imgs: [
        "//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg",
        "http://img1.qunarzz.com/wugc/p180/201306/16/7f08e81624346b1693835fbb.jpg_r_800x800_5f03ad73.jpg",
        "http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_r_800x800_c59f0eba.png"
      ]
    };
  },
  components: {
    commonGallary
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true;
    },
    handleBannerClose() {
      this.showGallary = false;
      console.log("a");
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

