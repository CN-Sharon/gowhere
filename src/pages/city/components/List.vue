<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item in hotCities" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list" v-for="innerItem of item" :key="innerItem.id">
          <div class="item border-bottom">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        // 因为this.$refs[this.letter]打印出来是一个数组，而我们要的是dom元素，所以后面加上[0]即可
        const element = this.$refs[this.letter][0]
        // this.scroll.scrollToElement(dom元素)
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .border-topbottom
    &.before
      border-color: #ccc
    &.after
      border-color: #ccc
  .border-bottom
    &.before
      border-color: #ccc
  .list
    position: absolute
    top:1.58rem
    left:0
    bottom:0
    right:0
    overflow:hidden
    .title
      line-height: .54rem
      background :#eee
      padding-left : .2rem
      color:#666
      font-size: .26rem
    .button-list
      overflow: hidden
      padding: .1rem .6rem .1rem .1rem
      .button-wrapper
        float: left
        width:33.33%
        .button
          height : .44rem
          line-height : .44rem
          margin: .1rem
          text-align:center
          box-sizing :border-box
          border:0.02rem solid #ccc
          border-radius : .06rem
    .item-list
      .item
        line-height :.76rem
        padding-left : .2rem

</style>
