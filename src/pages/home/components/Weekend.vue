<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name:'HomeWeekend',
  data () {
    return {
      recommendList:[
        {
          id:'001',
          imgUrl:'http://img1.qunarzz.com/sight/source/1505/5e/6e13db8af6ec30.jpg_r_640x214_5c1b0fa9.jpg',
          title:'三亚必打卡',
          desc:'玩转海岛热带雨林，感受独特黎苗文化'
        },
        {
          id:'002',
          imgUrl:'http://img1.qunarzz.com/sight/source/1511/1d/fe098e8cfec117.jpg_r_640x214_a9be292a.jpg',
          title:'上海城市观光',
          desc:'来这里寻找你所不认识的魔都 ，感受云端漫步，品味老上海风情，享受休闲时光'
        },
        {
          id:'003',
          imgUrl:'http://img1.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
          title:'京城溜娃必去',
          desc:'德智体美劳全面发展的亲子日，这些地方该去看看…'
        },
        {
          id:'004',
          imgUrl:'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          title:'寻找北京的皇城范儿',
          desc:'数百年的宫廷庙宇，至今依旧威严霸气'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    margin-top: .2rem
    text-indent: .2rem
    background-color: #eee
  .item-img-wrapper
    height: 0
    overflow: hidden
    padding-bottom: 33.9%
    .item-img
      width: 100%
  .item-info
    padding:.1rem
  .item-title
    line-height:.54rem
    fons-size: .32rem
    ellipsis()
  .item-desc
    line-height: .4rem
    color: #bbb
    font-size: .24rem
    ellipsis()
      
</style>