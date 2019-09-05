<template>
  <div>
      <detail-header></detail-header>
      <detail-banner></detail-banner>
      <detail-list></detail-list>
  </div>
</template>

<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/banner'
import  DetailList from './components/banner'
export default{
  name:'Detail',
  components:{
    DetailHeader,
    DetailBanner,
    DetailList
  }
}
</script>

<style lang="stylus" scoped>
</style>
