<template>
  <div>
    <div class="item"
    v-for="(item, index) of list"
    :key="index">
      <div class="item-title border-bottom">
        <span class="iconfont item-title-icon">&#xe6ac;</span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding 0 .2rem
    .item-title-icon
      position relative
      display: inline
      width .36rem
      height .36rem
      background-size: .4rem .3rem
  .item-children
    padding: 0 .3rem
</style>
