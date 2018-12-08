<template>
  <ul class="list">
    <li
      class="item"
      v-for="item in letters"
      :key="item"
      :ref="item"
      @click="handleLetterClick"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: "CityAlphabet",
  props: {
    list: Object
  },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.list) {
        letters.push(i);
      }
      return letters;
    }
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    };
  },
  updated() {
    this.startY = this.$refs["A"][0].offsetTop;
  },
  methods: {
    handleLetterClick(e) {
      this.$emit("change", e.target.innerText);
      // console.log(e.target.innerText)
    },
    handleTouchStart() {
      this.touchStatus = true;
    },
    handleTouchMove(e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.timer = setInterval(() => {
          //  console.log(startY)
          const touchY = e.touches[0].clientY - 35;
          const index = Math.floor((touchY - this.startY) / 20);
          //  console.log(index)
          if (index >= 0 && index < this.letters.length) {
            this.$emit("change", this.letters[index]);
          }
          //  console.log(e)
        }, 16);
      }
    },
    handleTouchEnd() {
      this.touchStatus = false;
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 0.6rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
  // background: red
}

.item {
  line-height: 0.4rem;
  text-align: center;
  color: $bgColor;
}
</style>