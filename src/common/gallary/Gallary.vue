<template>
  <div class="container" @click="handleGrallaryClick">
    <div class="warrper">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="(item,index) in imgs" :key="index">
          <img
            class="swipe-img"
            :src="item"
          >
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
        <!-- <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: "commonGallary",
  props:{
      imgs:{
          type: Array,
          default (){
              return []
          }
      }
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true,
        paginationType: "fraction",
        observeParents :true,
        observer: true
      }
    };
  },
  methods:{
      handleGrallaryClick(){
          this.$emit('close')
      }
  }
};
</script>

<style lang="stylus" scoped>
.container  >>> .swiper-container {
  overflow: inherit;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 99;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  background: #000;
}

.warrper {
  width: 100%;
  height: 0;
  padding-bottom: 100%;
}

.swipe-img {
  width: 100%;
}

.swiper-pagination {
  color: #fff;
  bottom: -1rem;
}
</style>


