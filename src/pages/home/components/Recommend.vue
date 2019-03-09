<template>
  <div>
    <div class="title">热门推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name:'HomeRecommend',
  data () {
    return {
      recommendList:[
        {
          id:'001',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
          title:'深圳野生动物园',
          desc:'这里有优雅和呆萌并存的睫毛精'
        },
        {
          id:'002',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title:'故宫',
          desc:'世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id:'003',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg',
          title:'八达岭长城',
          desc:'不到长城非好汉'
        },
        {
          id:'004',
          imgUrl:'http://img1.qunarzz.com/sight/p0/201405/27/ef08b0cb4a5afb2f570e5c4dff5f743e.jpg_200x200_f3ad8918.jpg',
          title:'长隆国际大马戏剧院',
          desc:'跟着大马戏团一起party~'
        },
        {
          id:'005',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1801/4e/4ee5653be58dcb1a3.water.jpg_200x200_d169685d.jpg',
          title:'香港迪士尼乐园',
          desc:'中国第一座迪士尼乐园'
        },
        {
          id:'006',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1811/42/42958b9abc760e2aa3.img.jpg_200x200_09b6d404.jpg',
          title:'三亚千古情景区',
          desc:'置身传统黎村，领略黎族风情'
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
  .item
    display:flex
    height: 1.9rem
    overflow: hidden
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex:1
      padding:.1rem
      min-width:0
      .item-title
        line-height:.54rem
        fons-size:.32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #bbb
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top:.16rem
        background-color: #ff9300
        padding: 0 .1rem
        border-radius: .06rem
        color: #fff
        font-size: .2rem
</style>