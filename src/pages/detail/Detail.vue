<template>
  <div>
      <detail-header></detail-header>
      <detail-banner></detail-banner>
      <div class="content">
        <detail-list></detail-list>
      </div>
  </div>
</template>

<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/banner'
import  DetailList from './components/list'
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
