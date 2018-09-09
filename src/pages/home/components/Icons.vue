<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"
          v-for="item of page"
          :key="item.id"
        >
          <img class="icon-img" :src="item.imgUrl">
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'
  .icons >>> .swiper-container
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 50%
  .icons
    .icon
      float:left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        display: block
        width: 70%
        box-sizing : border-box
        padding-top : .1rem
        margin: 0 auto
      .icon-desc
        text-align:center
        margin-top: .1rem
        color: #212121
        font-size: .28rem
        ellipsis()

</style>
