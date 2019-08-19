<template>
<div>
	<div class="search">
		<input v-model="keyword" type="text" class="input-search" placeholder="输入城市或拼音"/>
	</div>
	<div 
		class="search-content"
		ref="search"
		v-show="keyword"
	>
		<ul>
			<li class="search-item" v-for="item in list">{{item.name}}</li>
			<li v-show="hasList">没有找到匹配项</li>
		</ul>
	</div>
</div>	
</template>

<script>
import Bscroll from 'better-scroll'
export default{
	name:'CitySearch',
	props:{
		cities:Object
	},
	data(){
		return{
			keyword:'',
			list:[],
			timer:null
		}
	},
	computed:{
		hasList(){
			return !this.list.length
		}
	},
	watch:{
		keyword(){
			if(this.timer){
				clearTimeout(this.timer)
			}
			if(!this.keyword){
				this.list=[]
				return
			}
			this.timer=setTimeout(()=>{
				const result=[]
				for (let i in this.cities){
					this.cities[i].forEach((value)=>
					{
						if(value.spell.indexOf(this.keyword)>-1||value.name.indexOf(this.keyword)>-1)
						{
							result.push(value)
						}
					}
					)
				}
			this.list=result
			},100)
		}
	},
	mounted(){
		this.scroll=new Bscroll(this.$refs.search)
	}
}
</script>

<style lang="stylus" scoped>
	@import '../../../assets/styles/varibles.styl'
	.search
		height:.72rem
		padding:.1rem
		background:$bgColor
		.input-search
			width:100%
			height:.62rem
			text-align:center
			border-radius:.06rem
			padding:0 .1rem
			box-sizing:border-box
			color:#666
	.search-content
		z-index:1
		top:1.58rem
		bottom:0
		right:0
		left:0
		position:absolute
		overflow:hidden
		background:#eee
		.search-item
			line-height:.62rem
			color:#666
			background:#eee
</style>
