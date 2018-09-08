<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="(item,index) of itemList" :key="index">
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
  data () {
    return {
      itemList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
        title: '广州必游TOP10',
        desc: '感受现代与传统相融合的广州'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/50/07fa9343791682.jpg_r_640x214_c8c3d798.jpg',
        title: '自然户外好去处',
        desc: '快快来到户外，感受花城的魅力'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ec/902725c4d56517.jpg_r_640x214_7a74d251.jpg',
        title: '羊城民俗风情游',
        desc: '品味羊城文化，感受羊城别样风情'
      }, {
        id: '004',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/6f/bf9ef732f8ad2e.jpg_r_640x214_c759559e.jpg',
        title: '宝贝亲子游乐地',
        desc: '宝贝闲不住，我们去哪儿呀'
      }]
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
