<template>
  <div>
    <router-link
      tag="div"
      class="header-abs"
      to="/"
      v-show="showAbs"
      >
        <div class="iconfont header-icon-back">&#xe658;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
        景点详情
    </div>
    <div class="container"></div>
  </div>
</template>

<script>
export default{
  name:'DetailHeader',
  data(){
    return{
      showAbs:true,
      opacityStyle:{
        opacity:0
      }
    }
  },
  methods:{
    handleScroll(){
      const top=document.documentElement.scrollTop
      if(top>60){
        let opacity=top/140
        opacity=opacity>1?1:opacity
         this.opacityStyle={
           opacity
         }
        this.showAbs=false
      }else{
        this.showAbs=true
      }
    }
  },
  activated(){
    window.addEventListener('scroll',this.handleScroll)
  },
  deactivated(){
    window.removeEventListener('scroll',this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import  '../../../assets/styles/varibles.styl'
  .header-abs
    position :absolute
    left :.2rem
    top:.2rem
    width:.8rem
    height :.8rem
    border-radius :.4rem
    background :rgba(0,0,0,.5)
    line-height :.8rem
    .header-icon-back
      color :#FFFF00
      font-size :.7rem
  .header-fixed
      position :fixed
      top: 0
      left: 0
      text-align: center
      background :$bgColor
      width 100%
      height :.7rem
      line-height :.7rem
  .container
      height :18rem
      width :100%
</style>
