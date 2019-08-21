<template>
	<div class="header">
		城市选择
		<router-link to="/">
			<div class="iconfont back-icon">&#xe658;</div>
		</router-link>
	</div>
</template>
<script>
export default{
	name:'CityHeader'
}
</script>
<style lang="stylus" scoped>
	@import '../../../assets/styles/varibles.styl'
	.header
		position:relative
		background:$bgColor
		height:.8rem
		color:#fff
		text-align:center
		line-height:.8rem
		.back-icon
			position:absolute
			top:0
			left:0
			width:.6rem
			height:.5rem
			font-size:.4rem
			color:#fff
</style>