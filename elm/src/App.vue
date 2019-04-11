<template>
  <div id="app">
    <v-header :seller="datas.seller"></v-header>
    <div class="tab">
      <div class="tab-item">
        <router-link to="/goods">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/ratings">评价</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/seller">商家</router-link>
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
  import header from './components/header/header.vue';
  import axios from 'axios';
  export default {
    name: 'App',
    data () {
      return {
        datas: {
          seller: {},
          goods: [],
          ratings: []
        }
      }
    },
    mounted () {
      axios.get('/static/data.json').then(res => {
        this.datas.seller = res.data.seller;
        this.datas.goods = res.data.goods;
        this.datas.ratings = res.data.ratings;
      })
    },
    components: {
      'v-header': header
    }
  }
  // scoped 表示当前模板和下面的支模板都应用这个样式
</script>
<style lang="stylus" rel="stylesheet/stylus">
  #app
    .tab
      display: flex
      width: 100%
      height: 40px
      line-height: 40px
      border-bottom: 1px solid rgba(7,17,27,.2)
      .tab-item
        flex: 1
        text-align: center
        .router-link-active
          color: red
</style>
