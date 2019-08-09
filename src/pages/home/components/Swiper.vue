<template>
	<div class="wrapper">
	  <swiper :options="swiperOption">
		<!-- slides -->
		<swiper-slide v-for="item in swiperList" :key=item.id>
			<img class="wrapper-img" :src="item.imgUrl">
		</swiper-slide>
		<!-- Optional controls -->
		<div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>

<script>
  export default {
    name: 'HomeSwiper',
    data() {
      return {
        swiperOption: {
			pagination:'.swiper-pagination',
			loop:true
		},
		swiperList:[{
			id:'0001',
			imgUrl:'static/images/11.jpeg'
		},{
			id:'0002',
			imgUrl:'static/images/9.jpeg'
		}
		]
      }
    }
  }
</script>
<style lang="stylus" scoped>
	.wrapper >>> .swiper-pagination-bullet-active
		background:#fff !important
	.wrapper-img
		width:100%
		height:3rem
</style>
