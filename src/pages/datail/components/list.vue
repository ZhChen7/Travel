<template>
  <div class="list">
    <div class="item" v-for="(item,index) of categoryList" :key="index">
      <div class="item-title">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
        <div v-if="item.children" class="item-children">
             <detail-list :categoryList="item.children"></detail-list>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "DetailList",
  props: {
    categoryList: Array
  }
};
</script>

<style lang="stylus" scoped>
.item-title {
  line-height: 0.8rem;
  font-size: 0.32rem;
  padding: 0 0.2rem;
  border-bottom 1px solid #eee
}

.item-title-icon {
  position: relative;
  left: 0.05rem;
  top: 0.05rem;
  display: inline-block;
  width: 0.36rem;
  height: 0.36rem;
  background: url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -0.45rem no-repeat; // s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
  margin-right: 0.1rem;
  background-size: 0.4rem 3rem;
}
.item-children
    padding: 0 .2rem

</style>


