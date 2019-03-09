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
  props:{
    recommendList:Array
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