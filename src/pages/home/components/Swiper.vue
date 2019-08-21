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
		props: {
		  swiperList: Array
		},
    data() {
      return {
        swiperOption: {
			pagination:'.swiper-pagination',
			loop:true
		}
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
