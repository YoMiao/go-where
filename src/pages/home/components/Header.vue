<template>
  <div class="header">
    <div class="header-left">
      <!-- <div class="iconfont back-icon">&#xe624;</div> -->
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'>
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="scss" scoped>
@import '~@styles/varibles.scss';
.header {
  display: flex;
  line-height: $headerHeight;
  line-height: 70px;
  background: $bgColor;
  color: #fff;
  .header-left {
    width: 50px;
    float: left;
    .back-icon {
      text-align: center;
      font-size: 30px;
    }
  }
  .header-input {
    flex: 1;
    height: 50px;
    line-height: 50px;
    margin: auto 0;
    // margin-top: 6px;
    // margin-left: 6px;
    padding-left: 5px;
    background: #fff;
    border-radius: 5px;
    color: #ccc;
    font-size: 20px;
  }
  .header-right {
    min-width: 52px;
    padding: 0 10px;
    float: right;
    text-align: center;
    color: #fff;
    font-size: 23px;
    .arrow-icon {
      margin-left: -2px;
      font-size: 12px;
    }
  }
}
</style>
