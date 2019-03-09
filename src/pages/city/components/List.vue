<template>
  <div class="list" ref="wrapper">
    <div>
        <div class="area">
          <div class="title border-topbottom">您的位置</div>
          <div class="button-list">
            <div class="button-wrapper">
              <div class="button">北京</div>
            </div>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper" v-for="item of hotCities" :key="item.id">
              <div class="button">{{item.name}}</div>
            </div>
          </div>
        </div>
        <div class="area" v-for="(itemArr,key) of cities" :key="key">
          <div class="title border-topbottom" >{{key}}</div>
          <div class="item-list">
            <div class="item border-bottom" v-for="subItem of itemArr" :key="subItem.id">{{subItem.name}}</div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name:'CityList',
    props:{
        hotCities: Array,
        cities: Object
    },
    mounted () {
        const scroll = new BScroll(this.$refs.wrapper)
    }
}
</script>


<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  
    .border-topbottom
      &:before
        border-color #777777
      &:after
        border-color #777777
    .border-bottom
      &:before
        border-color #777777
  .list
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    .title
      line-height .54rem
      background-color #eee
      padding-left .2rem
      color #666
      font-size .26rem
    .button-list
      overflow hidden
      padding .1rem
      padding-right .5rem
      .button-wrapper
        float left
        width 33.3%
        .button
          margin .1rem
          text-align center
          padding .1rem 0
          border .02rem solid #cccccc
          border-radius .1rem
    .item-list
      .item
        line-height .76rem
        padding-left .2rem

</style>
