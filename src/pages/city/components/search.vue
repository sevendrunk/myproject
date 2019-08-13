<template>
	<div class="search">
		<input type="text" class="input-search" placeholder="输入城市或拼音"/>
	</div>
</template>

<script>
export default{
	name:'CitySearch'
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
</style>
