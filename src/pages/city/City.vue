<template>
  <div>
<<<<<<< HEAD
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
=======
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alphabet></city-alphabet>
>>>>>>> origin/city-list
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
<<<<<<< HEAD
=======
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
>>>>>>> origin/city-list
export default {
  name: 'City',
  components: {
    CityHeader,
<<<<<<< HEAD
    CitySearch
=======
    CitySearch,
    CityList,
    CityAlphabet
>>>>>>> origin/city-list
  }
}
</script>

<style lang="stylus" scoped>

</style>
