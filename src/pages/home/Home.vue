<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>


<script>
import HomeHeader from './components/Header' 
import HomeSwiper from './components/Swiper' 
import HomeIcons from './components/Icons' 
import HomeRecommend from './components/Recommend' 
import HomeWeekend from './components/Weekend' 
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name:'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      lastCity: '',
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    }
  },
  computed:{
    ...mapState(['city'])
  },
  methods:{
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city)
        .then(this.getHomeInfoSuccess)
    },
    getHomeInfoSuccess (res) {
      res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  // 使用activated钩子，该钩子只在keep-alive 组件停用时调用,而在服务器端渲染期间不被调用
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()    // 改变城市的时候，重新发一次请求，请求相对应的城市首页
    }

  }
}
</script>


<style>

</style>
