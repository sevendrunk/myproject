<template>
	<div>
		<div class="recommend-title">热销推荐</div>
		<ul>
			<li class="item" v-for="item of itemList" :key="item.id">
				<div class="item-img-wrap">
					<img class="item-img" :src="item.imgUrl"/>
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>
<script>
export default{
	name:'HomeRecommend',
	data(){
		return{
			itemList:[{
				id:'0001',
				imgUrl:'static/images/7a0edf873aa4cb02.jpg_r_390x260x90_70d91262.jpg',
				title:'大连海洋馆',
				desc:'浪漫大连,海洋主题乐园浪漫大连,海洋主题乐园浪漫大连,海洋主题乐园浪漫大连,海洋主题乐园浪漫大连,海洋主题乐园'
			},
			{
				id:'0002',
				imgUrl:'static/images/recom-1.jpg',
				title:'大连海洋馆',
				desc:'浪漫大连,海洋主题乐园'
			},
			{
				id:'0003',
				imgUrl:'static/images/recom-2.jpg',
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
		display:flex
		height:1.9rem
		.item-img
			width:1.7rem
			height:1.7rem
			padding:.1rem
		.item-info
			flex:1
			padding:.1rem
			min-width:0
			.item-title
				line-height:.54rem
				font-size:.32rem
				overflow:hidden
				white-space:nowrap
				text-overflow:ellipsis
			.item-desc
				ellipsis()
				line-height:.4rem
				color:#ccc
			.item-button
				margin-top:.2rem
				background:#ff9300
				border-radius:.06rem
</style>