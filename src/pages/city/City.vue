<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alpha-bet></city-alpha-bet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphaBet from './components/AlphaBet'
export default {
  name:'City',
  components:{
      CityHeader,
      CitySearch,
      CityList,
      CityAlphaBet
  }
}
</script>


<style lang="stylus" scoped>
    
</style>
