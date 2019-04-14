<template>
  <div>
    <div class="list-item border-bottom" v-for="(item,index) of categoryList" :key="index">
      <div class="item-title">
        <span class="ticket-icon"></span>
        <span class="ticket-name">{{item.title}}</span>
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :categoryList="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'DetailList',
  props:{
    categoryList:Array
  }
}
</script>

<style lang="stylus" scoped>
  .list-item
    padding: 0 0 0 .2rem
    font-size: .32rem
    color: #333
    .item-title
      position: relative
      height: .76rem
      line-height: .76rem
      border-bottom: .02rem solid #ccc
      .ticket-name
        padding-left: .5rem
      .ticket-icon
        display: inline-block
        position: absolute
        top: 0.2rem
        left: 0
        width: .36rem
        height: .36rem
        background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
        background-size: .4rem 3rem
    .item-children
      padding: 0 0 0 .2rem
</style>