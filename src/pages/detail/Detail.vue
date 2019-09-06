<template>
  <div>
      <detail-header></detail-header>
      <detail-banner
          :sightName="sightName"
          :bannerImg="bannerImg"
          :gallaryImgs="gallaryImgs"
      ></detail-banner>
      <div class="content">
        <detail-list :list="list"></detail-list>
      </div>
  </div>
</template>

<script>
import axios from 'axios'
import DetailHeader from './components/Header'
import DetailBanner from './components/banner'
import  DetailList from './components/list'
export default{
  name:'Detail',
  components:{
    DetailHeader,
    DetailBanner,
    DetailList
  },
  data(){
    return{
      sightName:'',
      bannerImg:'',
      gallaryImgs:[],
      list:[]
    }
  },
  methods:{
    getDetailInfo(){
      axios.get('/api/detail.json',{
        params:{
          id:this.$route.params.id
        }
      }
      ).then(this.getDetailData)
    },
    getDetailData(res){
       res=res.data
       if(res.data&&res.ret){
         const data=res.data
         this.sightName = data.sightName
         this.bannerImg = data.bannerImg
         console.log(this.bannerImg)
         this.gallaryImgs = data.gallaryImgs
         this.list = data.categoryList
       }
    }
  },
  mounted(){
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
</style>
