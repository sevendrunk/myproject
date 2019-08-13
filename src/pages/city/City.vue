<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
		<city-list  :cities="cities" :hot="hotCities"></city-list>
		<city-alphabet :cities="cities"></city-alphabet>
	</div>
</template>
<script>
import axios from 'axios'
import CityHeader from '../city/components/Header.vue'
import CitySearch from '../city/components/search.vue'
import CityList from '../city/components/list.vue'
import CityAlphabet from '../city/components/Alphabet.vue'
export default{
	name:'City',
	data(){
		return{
			cities:{},
			hotCities:[]
		}
	},
	components:{
		CityHeader,
		CitySearch,
		CityList,
		CityAlphabet
	},
	methods:{
		getCityInfo(){
			axios.get('/api/city.json')
			.then(this.getSucc)
		},
		getSucc(res){
			res=res.data
			if(res.ret&&res.data){
				this.cities=res.data.cities
				this.hotCities=res.data.hotCities
			}
		}
	},
	mounted(){
		this.getCityInfo()
	}
}
</script>
<style lang="stylus" scoped>
	
</style>