<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-desc">
        <div class="benner-title">{{sightName}}</div>
        <div class="banner-icon"><span class="iconfont">&#xe626;{{this.gallaryImgs.length}}</span></div>
      </div>
    </div>
    <banner-animation>
      <common-gallery v-show="showGallery" @close="handleBannerClose" :imgs="gallaryImgs"></common-gallery>
    </banner-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import BannerAnimation from 'common/animate/Animation'
export default {
  name:'DetailBanner',
  props:{
    gallaryImgs:Array,
    sightName:String,
    bannerImg:String
  },
  components:{
    CommonGallery,
    BannerAnimation
  },
  data () {
    return {
      showGallery:false,
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleBannerClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .banner
    overflow hidden
    height 0
    padding-bottom 55%
    position relative
    .banner-img
      width 100%
    .banner-desc
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.6))
      .benner-title
        flex 1
        padding 0 .2rem
        font-size .32rem
      .banner-icon
        line-height .32rem
        height .32rem
        padding 0 .4rem
        margin-top .14rem
        text-align center        
        font-size .32rem
        background rgba(0,0,0,0.6)
        border-radius .2rem
        .iconfont
          font-size .28rem        
</style>