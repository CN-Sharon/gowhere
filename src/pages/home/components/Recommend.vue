<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of list" :key="index">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
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

  .recommend-title
    line-height: .8rem
    margin-top: .2rem
    text-indent: .2rem
    background: #eee
  .item
    overflow: hidden
    height: 2.1rem
    display: flex
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding :.2rem
    .item-info
      flex:1
      min-width: 0
      padding :.1rem .1rem .1rem 0
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
