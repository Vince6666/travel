<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hotCities="hotCities"></city-list>
    <city-alpha-bet :cities="cities"></city-alpha-bet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphaBet from './components/AlphaBet'
import axios from 'axios'
export default {
  name:'City',
  components:{
      CityHeader,
      CitySearch,
      CityList,
      CityAlphaBet
  },
  data () {
    return {
      hotCities:[],
      cities:{}
    }
  },
  methods:{
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSuccess)
    },
    getCityInfoSuccess (res) {
      res = res.data
      if(res.ret && res.data) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
      
    }
  },
  mounted () {
    this.getCityInfo();
  }
}
</script>


<style lang="stylus" scoped>
    
</style>
