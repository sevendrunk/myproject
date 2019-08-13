<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
	</div>
</template>
<script>
import CityHeader from '../city/components/Header.vue'
import CitySearch from '../city/components/search.vue'
export default{
	name:'City',
	components:{
		CityHeader,
		CitySearch
	}
}
</script>
<style lang="stylus" scoped>
	
</style>