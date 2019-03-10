<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_600x330_b5e86902.jpg" alt="">
      <div class="banner-desc">
        <div class="benner-title">长隆野生动物世界(AAAAA景区)</div>
        <div class="banner-icon"><span class="iconfont">&#xe626;30</span></div>
      </div>
    </div>
    <common-gallery v-show="showGallery" @close="handleBannerClose" :imgs="imgs"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name:'DetailBanner',
  components:{
    CommonGallery
  },
  data () {
    return {
      showGallery:false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1605/d4/d4e2dce9d328d5b290.img.jpg_r_800x800_892973df.jpg', 'http://img1.qunarzz.com/sight/p0/1605/33/337228a10035958490.img.jpg_r_800x800_cf338d45.jpg']
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