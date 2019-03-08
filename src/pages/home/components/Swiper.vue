<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
      </swiper-slide>

        <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>


<script>
export default {
  name:'HomeSwiper',
  data() {
    return {
      swiperOption:{
        pagination: '.swiper-pagination',
        loop:true
      },
      swiperList:[
        {
          id:'0001',
          imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/0a8f7c789d0e62966e2485d33bf7ebd3.jpg_750x200_b455610d.jpg'
        },
        {
          id:'0002',
          imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/9f73976e40c4ef845cabe0efc0269ebb.jpg_750x200_aab92b7a.jpg'
        },
        {
          id:'0003',
          imgUrl:'http://img1.qunarzz.com/piao/fusion/1809/61/44400d6591891202.jpg_750x200_7565a05c.jpg'
        }
      ]
    }
  }
}
</script>


<style lang="stylus" scoped>
  // >>> 表示让样式进行穿透，即.wrapper下只有出现.swiper-pagination-bullet-active就应用样式，而不受scoped影响
  .wrapper >>> .swiper-pagination-bullet-active 
    background-color: #fff
  .wrapper
    width: 100%
    height: 0
    padding-bottom: 26.67%
    overflow: hidden
    .swiper-img
      width: 100%
</style>
