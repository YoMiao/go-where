<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="scss" scoped>
@import '~@styles/varibles.scss';
.header {
  position: relative;
  display: block;
  overflow: hidden;
  // height: $headerHeight;
  line-height: $headerHeight;
  text-align: center;
  color: #fff;
  background: $bgColor;
  font-size: 35px;
  padding: 10px 0;
  width: 100%;
  .header-back {
    // display: block;
    position: absolute;
    top: 50%;
    left: 0;
    transform: translate(0, -50%);
    width: 50px;
    text-align: center;
    font-size: 30px;
    color: #fff;
  }
}
</style>
