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
				imgUrl:'static/images/7a0edf873aa4cb02.jpg_r_390x260x90_70d91262.jpg',
				title:'新疆风景区',
				desc:'浪漫新疆,净化心灵之地'
			},
			{
				id:'0002',
				imgUrl:'static/images/7a0edf873aa4cb02.jpg_r_390x260x90_70d91262.jpg',
				title:'新疆风景区',
				desc:'浪漫新疆,净化心灵之地'
			},
			{
				id:'0003',
				imgUrl:'static/images/7a0edf873aa4cb02.jpg_r_390x260x90_70d91262.jpg',
				title:'新疆风景区',
				desc:'浪漫新疆,净化心灵之地'
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
		.item-img
			width:100%
			height:2.4rem
		.item-info
			flex:1
			padding:.1rem
			min-width:0
			.item-title
				line-height:.54rem
				font-size:.36rem
				font-weight:600
			.item-desc
				line-height:.4rem
				color:#ccc
</style>