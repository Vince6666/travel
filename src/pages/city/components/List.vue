<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">您的位置</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
               v-for="item of hotCities"
               :key="item.id"
               @click="handleCityClick(item.name)"     
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" 
            v-for="(itemArr,key) of cities" 
            :key="key" 
            :ref="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" 
               v-for="subItem of itemArr" 
               :key="subItem.id"
               @click="handleCityClick(subItem.name)"
          >
          {{subItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState , mapMutations } from 'vuex'
export default {
  name:'CityList',
  props:{
    hotCities: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity:'city'
    })
  },
  methods: {
    handleCityClick (city) {
      // this.$store.commit('changeCity',city)  //  可用下一行代码代替
      this.changeCity(city)       // 使用了mapMutations，把mutations中的changeCity映射到这个组件中的changeCity方法里
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch:{
    letter () {
      if(this.letter){
        var element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper,{
      click:true    // better-scroll 默认会阻止浏览器的原生 click 事件，开启点击事件(解决部分浏览器click无效的问题)
    })
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
