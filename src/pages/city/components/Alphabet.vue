<template>
	<ul class="list">
		<li class="item"  v-for="(item,key) of cities" :key="key"
		@click="handleClick"
		>{{key}}</li>
	</ul>
</template>

<script>
export default{
	name:'CityAlphabet',
	props:{
		cities:Object
	},
	methods:{
		handleClick(e){
			this.$emit('change',e.target.innerText)
		}
	}
}
</script>

<style lang="stylus" scoped>
	@import '../../../assets/styles/varibles.styl'
	.list
		display:flex
		flex-direction:column
		justify-content:center
		position:absolute
		top:3rem
		right:0
		bottom:0
		width:.4rem
		.item
			text-align:center
			color:$bgColor
			padding-bottom:.05rem
</style>
