<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="header-left">
        <span class="iconfont icon">&#xe600;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    height:$headerHeight
    line-height:$headerHeight
    background:$bgcolor
    color:#fff
    text-align: center
    font-size:.35rem
    .header-left
      position: absolute
      left:0
      top:0
      width:.64rem
      .icon
        display:block
        text-align :center
        font-size:.32rem
        color: #fff
</style>
