<template>
  <div class="header">
	  <div class="header-left">
	  	<span class="iconfont back-icon">&#xe658;</span>
	  </div>
	  <div class="header-input">
	  	<span class="iconfont">&#xe63c;</span>输入城市游玩主题</div>
		<router-link to="/city">
		  <div class="header-right">
			{{this.city}}<span class="iconfont arrow-icon">&#xe65c;</span>
		  </div>
		</router-link>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
  name: 'HomeHeader',
  computed:{
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
	@import '~@/assets/styles/varibles.styl'
	.header
		line-height:.86rem
		display:flex
		background-color:$bgColor
		color:#fff
		.header-left
			width:.64rem
			float:left
			.back-icon
				text-align:center
				font-size:.4rem
		.header-input
			flex:1
			line-height:.64rem
			height:.64rem
			margin-top:.12rem
			margin-left:.2rem
			background-color:#fff
			border-radius:.1rem
			color:#ccc
			padding-left:.2rem
		.header-right
			width:1.24rem
			float:right
			text-align:center
			.arrow-icon
				font-size:.24rem
</style>
