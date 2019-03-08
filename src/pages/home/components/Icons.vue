<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img :src="item.iconUrl" class="icon-img-content">
          </div>
          <p class="img-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>


<script>
export default {
  name:'HomeIcons',
  data () {
    return {
      swiperOption: {
          autoplay:false
      },
      iconList:[
          {
            id: '001',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
            desc: '热门景点'
          },
          {
            id: '002',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
            desc: '一日游'
          },
          {
            id: '003',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
            desc: '北京必游'
          },
          {
            id: '004',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
            desc: '茶馆相声'
          },
          {
            id: '005',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            desc: '动植物园'
          },
          {
            id: '006',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
            desc: '珠江夜游'
          },
          {
            id: '007',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
            desc: '泡温泉'
          },
          {
            id: '008',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
            desc: '踏青赏花'
          },
          {
            id: '009',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
            desc: '海洋馆'
          },
      ]
    }
  },
  computed:{
    pages () {
        const pages = [];
        this.iconList.forEach((item,index) => {
            const page = Math.floor(index / 8)
            if(!pages[page]){
                pages[page] = []
            }
            pages[page].push(item)
        })
        return pages
    }
  }
}
</script>


<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
.icons
  overflow hidden
  height: 0
  padding-bottom: 50%
  .icon
    overflow: hidden
    position: relative
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing:border-box
      padding:.1rem
      .icon-img-content
        height: 100%
        display: block
        margin: 0 auto
    .img-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      color: $darkTextColor
      text-align:center
      ellipsis()
</style>
