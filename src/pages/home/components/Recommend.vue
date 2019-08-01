<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/' + item.id"
      >
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="scss" scoped>
@import '~@styles/mixins.scss';
.title {
  margin-top: 10px;
  line-height: 50px;
  background: #eee;
  font-size: 23px;
  text-indent: 15px;
}
.item {
  overflow: hidden;
  display: flex;
  // height: 120px;
  .item-img {
    width: 100px;
    height: 100px;
    padding: 5px;
  }
  .item-info {
    flex: 1;
    padding: 10px;
    min-width: 0;
    .item-title {
      line-height: 30px;
      font-size: 25px;
      @include ellipsis;
    }
    .item-desc {
      line-height: 30px;
      color: #ccc;
      font-size: 22px;
      @include ellipsis;
    }
    .item-button {
      line-height: 30px;
      margin-top: 8px;
      background: #ff9300;
      font-size: 23px;
      padding: 3px 10px;
      border-radius: 3px;
      color: #fff;
    }
  }
}
</style>
