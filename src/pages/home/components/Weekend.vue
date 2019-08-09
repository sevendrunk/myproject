<template>
	<div>
		<div class="recommend-title">周末去哪</div>
		<ul>
			<li class="item" v-for="item of itemList" :key="item.id">
				<div class="item-img-wrap">
					<img class="item-img" :src="item.imgUrl"/>
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>
<script>
export default{
	name:'HomeWeekend',
	data(){
		return{
			itemList:[{
				id:'0001',
				imgUrl:'static/images/weekend.jpg',
				title:'大连海洋馆',
				desc:'浪漫大连,海洋主题乐园'
			},
			{
				id:'0002',
				imgUrl:'static/images/weekend.jpg',
				title:'大连海洋馆',
				desc:'浪漫大连,海洋主题乐园'
			},
			{
				id:'0003',
				imgUrl:'static/images/weekend.jpg',
				title:'大连海洋馆',
				desc:'浪漫大连,海洋主题乐园'
			}
			]
		}
	}
}
</script>
<style lang="stylus" scoped>
	@import "~@/assets/styles/mixins.styl"
	.recommend-title
		line-height:.8rem
		margin-top:.1rem
		background:#eee
		text-indent:.2rem
	.item
		.item-img-wrap
			overflow:hidden
			.item-img
				width:100%
				height:1.7rem
				padding:.1rem
			.item-title
				line-height:.54rem
				font-size:.32rem
			.item-desc
				line-height:.4rem
				color:#ccc
</style>