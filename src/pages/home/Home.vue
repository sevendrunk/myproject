<template>
  <div>
		<home-header></home-header>
		<home-swiper :swiperList="swiperList"></home-swiper>
		<home-icons :iconList="iconList"></home-icons>
		<home-recommend ></home-recommend>
		<home-weekend :itemList="weekendList"></home-weekend>
	</div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icon'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
export default {
  name: 'Home',
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecommend,
		HomeWeekend
	},
	data(){
		return{
			swiperList:[],
			iconList:[],
			weekendList:[]
		}
	},
	methods:{
		swiperInfo(){
			axios.get('/api/index.json')
			.then(this.Succ)
			},
		Succ(res){
			res=res.data
			if(res.ret&&res.data){
				const data=res.data
				this.swiperList=data.swiperList,
				this.iconList=data.iconList,
				this.weekendList=data.weekendList
			}
		}
		},
	mounted(){
		this.swiperInfo()
	}
}
</script>

<style scoped>
</style>