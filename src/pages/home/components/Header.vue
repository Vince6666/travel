<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市、景点
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>


<script>
export default {
  name:'HomeHeader',
  props:{
    city:String
  }
}
</script>


<style lang="stylus" scoped>
  // @import '../../../assets/styles/varibles.styl'   // 这样写路径台复杂,下面的写法性能更加优化
  // @import '~@/assets/styles/varibles.styl'     // 使用 @ 前面再加上 ~ 来表示 src 目录，实际上这是webpack的默认配置项，
                                                  // 我们也可以自己在build目录下的webpack.base.conf.js里面的alias选项添加其他配置，
                                                  // 配置后会报警告，通过重启服务可以解决问题
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: $headerHeight
    color: #ffffff
    background-color: $bgColor
    .header-left
      float: left
      width: 0.64rem
      .back-icon
        text-align: center
        font-size:.4rem
    .header-input
      flex:1
      height: .64rem
      line-height: .64rem
      background-color: #fff
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      border-radius: .1rem
      color: #ccc
    .header-right
      float: right
      width: 1.24rem
      text-align: center
      color: #fff
      .arrow-icon
        font-size:.24rem 

</style>
