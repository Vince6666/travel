<template>
  <div>
    <router-link to="/" tag="div" class="header-back" v-show="showAbs">
      <span class="iconfont header-back-icon">&#xe624;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link to="/">  
        <div class="iconfont arrow-icon">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name:'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
          opacity: 0
      }
    }
  },
  methods:{
    handleScroll () {
      const top = document.documentElement.scrollTop || document.body.scrollTop
      if (top > 50) {
        this.showAbs = false
        let opacity = top / 200
        if(opacity > 1) {
          opacity = 1
        }
        this.opacityStyle.opacity = opacity
      } else {
          this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll',this.handleScroll)
  },
  unmounted () {      // 对上面绑定的全局事件进行解绑
    window.removeEventListener('scroll',this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-back
    position: absolute
    top: 0.2rem
    left: 0.2rem
    background: rgba(0,0,0,0.6)
    width: 0.8rem
    height: 0.8rem
    line-height: .8rem
    border-radius: .4rem
    text-align: center
    .header-back-icon
      color: #ffffff
      font-size: .4rem
  .header-fixed
    z-index: 999 
    position: fixed
    top: 0
    left: 0
    right: 0
    height: $headerHeight
    line-height: $headerHeight
    overflow: hidden
    background-color: $bgColor
    color: #fff
    font-size: .32rem
    text-align: center
    .arrow-icon
      position: absolute
      left: 0 
      top: 0
      font-size: .4rem 
      width: .64rem
      text-align: center
      color: #fff
</style>