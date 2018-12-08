<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities"></city-list>
    <city-alphabet :list="cities"></city-alphabet>
  </div>
</template>


<script>
import axios from "axios";
import CityHeader from "./components/Header";
import CitySearch from "./components/search";
import CityList from "./components/List";
import CityAlphabet from "./components/Alphabet";

export default {
  name: "City",
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data() {
    return {
      cities: {},
      hotCities: []
    };
  },
  methods: {
    getCityInfo() {
      axios.get("/api/city.json").then(this.handleGetCityInfoSucc);
    },
    handleGetCityInfoSucc(res) {
		res =res.data
		if(res.ret && res.data){
			const data= res.data
			console.log(data)
			this.cities=data.cities
			this.hotCities=data.hotCities
			console.log(this.cities)
		}
    }
  },
  mounted() {
    this.getCityInfo();
  }
};
</script>

<style lang="stylus" scoped>
</style>