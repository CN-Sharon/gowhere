<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of itemList" :key="index">
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
  data () {
    return {
      itemList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
        title: '长隆野生动物世界',
        desc: '夏日缤纷，与家人好友结伴而行，长隆野生动物世界欢迎您'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_200x200_b9e4ac2c.jpg',
        title: '长隆欢乐世界',
        desc: '和家人一起游览各种动物'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_200x200_3c429960.jpg',
        title: '长隆国际大马戏剧院',
        desc: '夏日缤纷，与家人好友结伴而行，长隆野生动物世界欢迎您'
      }, {
        id: '004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_200x200_b902dd9e.jpg',
        title: '长隆水上乐园',
        desc: '和家人一起游览各种动物'
      }]
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
