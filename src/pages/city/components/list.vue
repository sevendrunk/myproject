<template>
	<div class="list" ref="wrapper">
	<div>
		<div class="area">
			<div class="title">当前城市</div>
			<div class="button-list">
				<div class="button-wrapper">
					<div class="button">{{this.$store.state.city}}</div>
				</div>
			</div>	
		</div>
		<div class="area">
			<div class="title">热门城市</div>
			<div class="button-list">
				<div class="button-wrapper" v-for="item of hot" :key="item.id">
					<div class="button">{{item.name}}</div>
				</div>
			</div>	
		</div>
		<div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
			<div class="title">{{key}}</div>
			<div class="item-list">
				<div class="item" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
			</div>
		</div>
	</div>
	</div>
</template>

<script>
import Bscroll from 'better-scroll'
export default{
	name:'CityList',
	props:{
		hot:Array,
		cities:Object,
		letter:String
	},
	mounted(){
		this.scroll=new Bscroll(this.$refs.wrapper)
	},
	watch:{
		letter(){
			if(this.letter){
				const element=this.$refs[this.letter][0]
				this.scroll.scrollToElement(element)
			}
		}
	}
}
</script>

<style lang="stylus" scoped>
	.list
		position:absolute
		overflow:hidden
		top:0
		left:0
		bottom:0
		top:1.7rem
		width:100%
		.title
			width:100%
			line-height:.44rem
			padding-left:.2rem
			color:#666
			background:#ccc
			border-bottom:1px solid #eee
		.button-list
			overflow:hidden
			padding: .1rem .6rem .1rem .1rem
			width:100%
			.button-wrapper
				width:33.3%
				float:left
				.button
					margin: .1rem .3rem
					padding: .1rem
					text-align: center
					border: .02rem solid #ccc
					border-radius: .06rem
		.item-list
			.item
				line-height:.76rem
				color:#666
				padding-left:.2rem
				border-bottom:1px solid #eee
</style>
