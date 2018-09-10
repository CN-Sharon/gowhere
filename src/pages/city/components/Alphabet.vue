<template>
  <ul class="list">
    <li class="item"
      v-for="item of letters"
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
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    // startY是指A的Y轴位置
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        // 设置定时器，隔16毫秒后才会再次触发，限流
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          // e.touches[0]指手指的位置信息，e.touches[0].clientY是获取手指距离手机顶部的y轴坐标，
          // 减去79,是指减去蓝色输入框等部分的高度
          const touchY = e.touches[0].clientY - 79
          // 20 是一个字母的高度，index代表滑动后是在第几个字母处,Math.floor()取整数
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .list
    display :flex
    flex-direction: column
    justify-content :center
    position: absolute
    bottom: 0
    right:0
    top:1.58rem
    width:0.6rem
    color :$bgcolor
    .item
      text-align :center
      line-height:.4rem
</style>
