<template>
  <div>
    <div
      class="item"
      v-for="(item, index) of list"
      :key="index"
    >
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-chilren">
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

<style lang="scss" scoped>
.item-title-icon {
  position: relative;
  left: px;
  top: 3px;
  display: inline-block;
  width: 18px;
  height: 18px;
  background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -22.5px no-repeat;
  margin-right: 10px;
  background-size: 20px 150px;
  transform: scale(2);
}
.item-title {
  line-height: 50px;
  font-size: 20px;
  padding: 0 20px;
}
.item-chilren {
  padding: 0 20px;
}
</style>
