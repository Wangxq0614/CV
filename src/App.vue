<template>
  <div class="wxq">
    <img class="wxq-logo" src="@/assets/logo.jpg" alt="" />
    <h3 class="wxq-title">嗯!</h3>
    <ul class="wxq-menu">
      <li
        class="wxq-menu-item"
        v-for="(item, index) in menusList"
        :key="index"
        @click="handleClick(item.url)"
      >
        <img :src="item.icon" :alt="item.nam" />
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const menusList = ref([
  {
    icon: new URL('@/assets/GitHub.svg', import.meta.url).href,
    name: 'github',
    url: 'https://github.com/Wangxq0614'
  },
  {
    icon: new URL('@/assets/gitee.svg', import.meta.url).href,
    name: 'gitee',
    url: 'https://gitee.com/wangxq0614'
  },
  {
    icon: new URL('@/assets/x.svg', import.meta.url).href,
    name: 'x',
    url: 'https://twitter.com/wangxq0614'
  },
  {
    icon: new URL('@/assets/weibo.svg', import.meta.url).href,
    name: 'weibo',
    url: 'https://weibo.com/u/3123641197'
  }
])
function handleClick(url) {
  window.open(url)
}
</script>

<style lang="scss" scoped>
.wxq {
  width: 100vw;
  height: 100vh;
  background-color: #333;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .wxq-logo {
    width: 150px;
    height: 150px;
    border-radius: 50%;
  }
  .wxq-title {
    margin: 30px 0;
    color: #dcdcdc;
  }

  .wxq-menu {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 30px;
    padding-left: 0;
    .wxq-menu-item {
      list-style: none;
      > img {
        width: 40px;
        height: 40px;
      }
    }
  }
}
</style>
