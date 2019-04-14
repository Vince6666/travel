<template>
  <ul class="list">
    <li class="item" 
        v-for="item of letters" 
        :key="item"
        :ref="item"
        @click="LetterClicked"
        @touchstart.prevent="handleTouchStart"
        @touchmove="handlTouchMove"
        @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
export default {
  name:'CityAlphaBet',
  props:{
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      lastTime: 0
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed:{
    letters () {
      const letters = []
      for(let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods:{
    LetterClicked(e) {
      this.$emit('change',e.target.innerHTML)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handlTouchMove (e) {
      if(this.touchStatus) {
        // 使用函数节流来限制快速的滑动操作
        let nowTime = Date.now()
        
        if (nowTime - this.lastTime > 30) {
          const touchY = e.targetTouches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          if(index >= 0 && index < this.letters.length) {
            this.$emit('change',this.letters[index])
          }
          this.lastTime = nowTime
        } else {
          return ''
        }
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
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
