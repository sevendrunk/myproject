<template>
	<ul class="list">
		<li :ref="item" class="item"  v-for="item of letters" :key="item"
		@click="handleClick"
		@touchstart="handleTouchStart"
		@touchmove="handleTouchMove"
		@touchend="handleTouchEnd"
		>{{item}}</li>
	</ul>
</template>

<script>
export default{
	name:'CityAlphabet',
	data(){
		return{
			touchStatus:false,
			startY:0,
			timer:null
		}
	},
	updated(){
		this.startY=this.$refs['A'][0].offsetTop
	},
	computed:{
		letters(){
			const letters=[]
			for(let i in this.cities){
				letters.push(i)
			}
			return letters
		}
	},
	props:{
		cities:Object
	},
	methods:{
		handleClick(e){
			this.$emit('change',e.target.innerText)
		},
		handleTouchStart(){
			this.touchStatus=true
		},
		handleTouchMove(e){
			if(this.touchStatus){
				if(this.timer){
					clearTimeout(this.timer)
				}
				this.timer=setTimeout(()=>{
					const touchY=e.touches[0].clientY-145
					const index=Math.floor((touchY-this.startY)/17)
					if(index>0&&index<this.letters.length){
					this.$emit('change',this.letters[index])
					}
				},16)
			}
		},
		handleTouchEnd(){
			this.touchStatus=false
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
