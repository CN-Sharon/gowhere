<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="(item,index) of list" :key="index">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'

  .weekend-title
    line-height: .8rem
    margin-top: .2rem
    text-indent: .2rem
    background: #eee
  .item
    .item-img
      width: 100%
    .item-info
      padding :.1rem
      .item-title
        font-size: .32rem
        line-height:.45rem
        padding-top .2rem
        ellipsis()
      .item-desc
        line-height:.56rem
        color:#ccc
        ellipsis()
      .item-button
        padding: .05rem .1rem
        line-height: .4rem
        color: #ffffff
        background: #ffbe1f
        border-radius: .06rem
</style>
