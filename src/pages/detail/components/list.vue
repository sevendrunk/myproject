<template>
  <div>
    <div class="item" v-for="(item,index) in list" :key="index">
        <div class="item-title">
          <span class="item-icon-title"></span>
          {{item.title}}
        </div>
        <div v-if="item.children" class="item-chilren">
          <detail-list :list="item.children"></detail-list>
        </div>
    </div>
  </div>
</template>

<script>
export default{
  name:'DetailList',
  props:{
     list:Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    line-height :.8rem
    font-size:.32rem
    padding:0 .2rem
  .item-chilren
    padding:0 .2rem
</style>
