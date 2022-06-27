<template>
  <div class="my-tab-bar">
    <div :class="['tab-item', {current: currentIndex === index}]" v-for="(item, index) in tabList" :key="index" @click="changeComponent(item.componentName, index)">
      <!-- 图标 -->
      <span :class="`iconfont ${item.iconText}`"></span>
      <!-- 文字 -->
      <span class="text">{{ item.text }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tabList: {
      type: Array,
      required: true,
      validator(data) {
        const len = data.length
        if (len > 2 && len < 5) {
          return true
        } else {
          throw new Error('数组都发错脑子坏掉了？')
        }
      }
    }
  },
  data() {
    return {
      currentIndex: ''
    }
  },
  methods: {
    changeComponent(compName, index) {
      this.currentIndex = index
      this.$emit('change-component', compName)
    }
  }
}
</script>

<style lang="less" scoped>
.my-tab-bar {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: white;
  .tab-item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.current {
  color: #1d7bff;
}
.text {
  margin-top: -10px;
}
</style>
