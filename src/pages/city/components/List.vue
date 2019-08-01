<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper"
            @click="handleCityClick(currentCity)">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item of hot"
            :key="item.id"
            @click="handleCityClick(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div
        class="area"
        v-for="(item, key) of cities"
        :key="key"
        :ref="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
            {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    //  由于better-scroll组件会默认禁止click事件，在移动端会产生bug，所以要加上click:true参数
    this.scroll = new Bscroll(this.$refs.wrapper, {click: true})
  }
}
</script>

<style lang="scss" scoped>
@import '~@styles/varibles.scss';
.border-topbottom {
  &:before {
    border-color: #ccc;
  }
  &:after {
    border-color: #ccc;
  }
}
.border-bottom {
  &:before {
    border-color: #ccc;
  }
}
.list {
  overflow: hidden;
  position: absolute;
  top: 130px;
  left: 0;
  right: 0;
  bottom: 0;
  .title {
    line-height: 45px;
    background: #eee;
    padding-left: 15px;
    color: #666;
    font-size: 23px;
  }
  .button-list {
    overflow: hidden;
    padding: 5px 30px 5px 5px;
    .button-wrapper {
      float: left;
      width: 33.33%;
      .button {
        margin: 5px;
        padding: 10px 0;
        text-align: center;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 25px;
      }
    }
  }
  .item-list {
    .item {
      line-height: 50px;
      padding-left: 20px;
      font-size: 25px;
    }
  }
}
</style>
