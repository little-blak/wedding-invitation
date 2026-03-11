<template>
  <div class="wedding-invitation">
    <!-- 封面组件 -->
    <Cover 
      v-if="currentView === 'cover'"
      :weddingDate="weddingInfo.date"
      :groomName="weddingInfo.groomName"
      :brideName="weddingInfo.brideName"
      @openInvitation="openInvitation"
    />
    
    <!-- 视频播放器组件 -->
    <VideoPlayer 
      v-else-if="currentView === 'video'"
      :videoSrc="videoSrc" 
      @video-ended="onVideoEnded"
    />
    
    <!-- 主内容区域 -->
    <div v-else class="main-content">
      <Invitation
        :groomName="weddingInfo.groomName"
        :brideName="weddingInfo.brideName"
        :weddingDate="weddingInfo.date"
        :weddingTime="weddingInfo.time"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, readonly } from 'vue'
import Cover from '@/components/Cover.vue'
import Invitation from '@/components/Invitation.vue'
import VideoPlayer from '@/components/VideoPlayer.vue'

// 页面视图状态枚举
const VIEW_STATES = {
  COVER: 'cover',
  VIDEO: 'video',
  CONTENT: 'content'
}

// 页面状态管理
const currentView = ref(VIEW_STATES.COVER)

// 婚礼信息（使用只读对象，因为这些数据通常不会在运行时改变）
const weddingInfo = readonly({
  groomName: '王超强', // 新郎姓名
  brideName: '安亚城', // 新娘姓名
  date: '2026-04-12', // 婚礼日期
  time: '12:00' // 婚礼时间
})

// 视频资源路径
const videoSrc = '你的视频路径.mp4'

/**
 * 打开邀请函
 * 切换到视频视图
 */
const openInvitation = () => {
  currentView.value = VIEW_STATES.VIDEO
  document.body.style.overflow = 'hidden' // 禁止页面滚动
}

/**
 * 视频播放结束
 * 切换到主内容视图
 */
const onVideoEnded = () => {
  currentView.value = VIEW_STATES.CONTENT
  document.body.style.overflow = 'auto' // 恢复页面滚动
}
</script>

<style scoped>
/* CSS变量定义 */
:root {
  --primary-bg: linear-gradient(180deg, #FFF5F5 0%, #F0F8FF 100%);
  --font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif;
  --max-width: 800px;
  --animation-duration: 1s;
}

.wedding-invitation {
  font-family: var(--font-family);
  background: var(--primary-bg);
  min-height: 100vh;
  max-width: var(--max-width);
  margin: 0 auto;
  position: relative;
}

.main-content {
  animation: fadeIn var(--animation-duration) ease-in-out;
}

/* 淡入动画 */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
