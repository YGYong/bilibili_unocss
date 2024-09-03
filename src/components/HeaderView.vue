<template>
  <div class="flex flex-nowrap">
    <div class="flex flex-shrink-0">
      <span v-for="item in sideContent" :key="item.id">{{ item.title }}</span>
    </div>
    <el-input v-model="searchVal" placeholder="Please Input" :suffix-icon="Search" class="flex-1" />
    <div class="flex flex-shrink-0">
      <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png" />
      <span v-for="item in rightContent" :key="item.id">{{ item.title }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Search } from '@element-plus/icons-vue'
const searchVal = ref('')
// 左侧功能
const sideContent = [
  { id: '1', title: '首页', path: '/' },
  { id: '2', title: '番剧', path: '/about' },
  { id: '3', title: '直播', path: '/liveBroadcast' },
  { id: '4', title: '游戏中心', path: '/gamesCenter' },
  { id: '5', title: '会员购', path: '/memberPurchase' },
  { id: '6', title: '漫画', path: '/caricature' },
  { id: '7', title: '赛事', path: '/competition' },
  { id: '8', title: '下载客户端', path: '/downloadClient' }
]
// 右侧功能
const rightContent = [
  { id: '1', title: '大会员', path: '/megaMember' },
  { id: '2', title: '消息', path: '/info' },
  { id: '3', title: '动态', path: '/dynamicState' },
  { id: '4', title: '历史', path: '/history' },
  { id: '5', title: '创作中心', path: '/creativeCenter' },
  { id: '6', title: '投稿', path: '/contribute' }
]
</script>

<style scoped></style>
