<template>
  <div>
    <div class="banner" @click="handleBannerClick">
     <img class="banner-img" :src="bannerImg"/>
    <div class="banner-info">
        <div class="banner-title">
            {{this.sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont">&#xe63c;</span>
          39
        </div>
    </div>
    </div>
    <common-gallary
     :imgs="gallaryImgs"
      v-show="showGallary"
      @close="handleGallaryClose"
      ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from '@/.././common/gallary/Gallary.vue'
export default{
  name:'DetailBanner',
  props:{
    sightName:String,
    bannerImg:String,
    gallaryImgs:Array
  },
  data(){
    return{
        showGallary:false
    }
  },
  components:{
    CommonGallary
  },
  methods:{
    handleBannerClick(){
      this.showGallary=true
    },
    handleGallaryClose(){
      this.showGallary=false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position :relative
    overflow :hidden
    height :0
    padding-bottom :50%
    .banner-img
      width 100%
    .banner-info
      display :flex
      position :absolute
      left: 0
      right:0
      bottom :0
      line-height :.6rem
      background-image :linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        color:white
        flex:1
        font-size 0.32rem
        padding:0 .2rem
      .banner-number
         color:white
         flex:1
         font-size 0.32rem
         border-radius :.2rem
         .iconfont
           font-size :.24rem
</style>
