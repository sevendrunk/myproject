<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl">
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>
<script>
export default{
	name:'HomeIcons',
	props:{
		iconList:Array
	},
	data(){
		return{
			swiperOption:{
				autoplay:false
			}
		}
	},
	computed:{
		pages:function(){
			const pages=[]
			this.iconList.forEach((item,index)=>{
				const page=Math.floor(index/8)
				if(!pages[page]){
					pages[page]=[]
				}
				pages[page].push(item)
			})
			return pages
		}
	}
}
</script>
<style lang="stylus" scoped>
	@import '~@/assets/styles/mixins.styl'
	.icons >>> .swiper-container
		height:0
		padding-bottom:4rem
	.icons
		margin-top:0.2rem
		margin-left:0.6rem
		.icon
			position:relative
			float:left
			width:25%
			height:0.3rem
			padding-bottom:1.5rem
			.icon-img
				position:absolute
				top:0
				left:0
			.icon-img-content
					width:.8rem
					height:.8rem
			.icon-desc
				position:absolute
				top:1rem
				left:0
				right:0
				ellipsis()
</style>