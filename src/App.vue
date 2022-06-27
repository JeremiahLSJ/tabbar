<template>
  <div class="app">
    <MyHeader></MyHeader>
    <MyFooter></MyFooter>
  </div>
</template>

<script>
import MyHeader from '@/components/MyHeader.vue'
import MyFooter from '@/components/MyFooter.vue'
// import MyUserInfo from '@/views/MyUserInfo.vue'
// import MyGoodsSearch from '@/views/MyGoodsSearch.vue'
// import MyGoodsList from '@/views/MyGoodsList.vue'
export default {
  components: {
    MyHeader,
    MyFooter
    // MyUserInfo,
    // MyGoodsSearch,
    // MyGoodsList
  },
  data() {
    return {
      tabList: [
        {
          iconText: 'icon-shangpinliebiao',
          text: '商品列表',
          componentName: 'MyGoodsList'
        },
        {
          iconText: 'icon-sousuo',
          text: '商品搜索',
          componentName: 'MyGoodsSearch'
        },
        {
          iconText: 'icon-user',
          text: '我的信息',
          componentName: 'MyUserInfo'
        }
      ],
      componentName: 'MyGoodsList'
    }
  }
}
</script>

<style scoped>
.app {
  padding: 50px 0;
}
</style>
