<template>
  <div class="detailHeader">
        <div class="header-fixed" v-show="showAbs" :style="opacityStyle">
          <router-link to="/">
            <span class="iconfont detail-back-icon">&#xe658;</span>
          </router-link>
          景点内容
        </div>
    </div>
</template>

<script>
export default{
  name:'DetailHeader',
  data(){
    return{
      showAbs:true,
      opacityStyle:{
        opacity:1
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
  .detailHeader
     position :relative
    .header-fixed
        position :fixed
        top:0
        left :0
        background-color: #00BCD4
        width: 100%
        z-index :99
        color :#000000
        text-align :center
        line-height :0.7rem
        .detail-back-icon
          top:0
          left:0
          position :absolute
          color :white
</style>
