<template>
  <div class="relative top-0 left-0 h-[180px]">
    <video
      class="absolute top-0 left-0 -z-1"
      src="@/assets/videos/1.mp4"
      autoplay
      muted
      loop
    ></video>
    <div class="flex flex-nowrap px-2 pt-2 h-[40px]">
      <div class="common_banner w-[40%]">
        <div v-for="item in sideContent" :key="item.id">
          <el-icon v-if="item.icon" class="mr-1 align-middle"><Download /></el-icon>
          <span>{{ item.title }}</span>
        </div>
      </div>
      <el-input
        v-model="searchVal"
        placeholder="Please Input"
        :suffix-icon="Search"
        size="small"
        class="flex-1 opacity-70"
      />
      <div class="common_banner w-[35%]">
        <el-avatar :src="avatar" />
        <div v-for="item in rightContent" :key="item.id" class="flex flex-col items-center">
          <!-- <el-icon>< item.icon /></el-icon> -->
          <component :is="item.icon" class="size-[18px]" />
          <span>{{ item.title }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import {
  Search,
  Download,
  Present,
  Message,
  Bell,
  Star,
  Clock,
  Medal
} from '@element-plus/icons-vue'
import avatar from '@/assets/images/users/avatar.jpg'
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
  { id: '8', title: '下载客户端', icon: '<el-icon><Download /></el-icon>', path: '/downloadClient' }
]
// 右侧功能
const rightContent = [
  { id: '1', title: '大会员', icon: Present, path: '/megaMember' },
  { id: '2', title: '消息', icon: Message, path: '/info' },
  { id: '3', title: '动态', icon: Bell, path: '/dynamicState' },
  { id: '4', title: '收藏', icon: Star, path: '/star' },
  { id: '5', title: '历史', icon: Clock, path: '/history' },
  { id: '6', title: '创作中心', icon: Medal, path: '/creativeCenter' },
  { id: '7', title: '投稿', path: '/contribute' }
]
</script>

<style lang="scss" scoped>
.common_banner {
  @apply "flex justify-between items-center flex-shrink-0 text-white mx-2";
}
</style>
