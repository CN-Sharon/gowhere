<template>
  <div>
    <div class="search">
        <input v-model="keyworld" class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" v-show="keyworld">
      <p class="item border-bottom" v-for="item of list" :key="item.id">{{item.name}}</p>
      <p class="item border-bottom" v-show="hasNoData">没有找到数据</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyworld: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyworld () {
      if (this.timer) {
        setTimeout(this.timer)
      }
      if (!this.list) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyworld) > -1 || value.name.indexOf(this.keyworld) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .search
    height 0.72rem
    padding :0 .1rem
    background:$bgcolor
    .search-input
      box-sizing:border-box
      width:100%
      height:.62rem
      line-height:.62rem
      text-align:center
      border-radius: 0.06rem
      color:#666
      background:#fff
  .search-content
    position: absolute
    top:1.56rem
    left:0
    right:0
    bottom:0
    z-index:1
    background: #ccc
    .item
      line-height: .56rem
      text-indent :.2rem
      color:#666
      background :#fff

</style>
