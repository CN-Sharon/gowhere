<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon">&#xe600;</span>
    </div>
    <div class="header-input">
      <span class="iconfont icon">&#xe601;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{this.city}}
      <span class="iconfont icon">&#xe625;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .header
    display:flex
    line-height:.86rem
    background:$bgcolor
    color:#fff
    .header-left
      width:.64rem
      float:left
      .icon
        display:block
        text-align :center
        font-size:.32rem
    .header-input
      flex:1
      height:.64rem
      line-height:.64rem
      margin-top:.12rem
      margin-left:.2rem
      background:#fff
      border-radius:.1rem
      color:#999
      span
        margin :0 .1rem 0 .2rem
        text-align :center
    .header-right
      width:1.24rem
      float:right
      text-align:center

</style>
