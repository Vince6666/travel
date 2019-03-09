<template>
  <ul class="list">
      <li class="item" v-for="(item,key) of cities" :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
    name:'CityAlphaBet',
    props:{
      cities: Object
    }
}
</script>


<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display flex
    flex-direction column
    justify-content center
    position absolute
    width .4rem
    top 1.58rem
    right 0
    bottom 0
    .item
      color $bgColor
      text-align center
      line-height .4rem
</style>
