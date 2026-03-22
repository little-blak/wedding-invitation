<template>
  <div class="music-player" :class="{ 'playing': isPlaying }" @click="togglePlay">
    <div class="music-icon">
      <svg v-if="isPlaying" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 19H4V5H6V19Z" fill="currentColor"/>
        <path d="M14 19H12V5H14V19Z" fill="currentColor"/>
      </svg>
      <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M8 5V19L19 12L8 5Z" fill="currentColor"/>
      </svg>
    </div>
    <div class="music-wave">
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isPlaying = ref(true)
let audio = null

// 音频文件路径（使用本地的白色球鞋音乐文件）
const musicSrc = new URL('@/assets/music/white_shoes.mp3', import.meta.url).href

// 初始化音频
const initAudio = () => {
  audio = new Audio(musicSrc)
  audio.loop = true
  audio.volume = 0.5
  
  // 自动播放
  audio.play().catch(error => {
    console.log('自动播放被阻止:', error)
    isPlaying.value = false
  })
}

// 切换播放/暂停
const togglePlay = () => {
  if (isPlaying.value) {
    audio.pause()
  } else {
    audio.play()
  }
  isPlaying.value = !isPlaying.value
}

// 组件挂载时初始化
onMounted(() => {
  initAudio()
})

// 组件卸载时清理
onUnmounted(() => {
  if (audio) {
    audio.pause()
    audio = null
  }
})
</script>

<style scoped>
.music-player {
  position: fixed;
  top: 20px;
  right: 20px;
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.9);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  z-index: 1000;
  transition: all 0.3s ease;
  color: #e94840;
}

.music-player:hover {
  transform: scale(1.1);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
}

.music-icon {
  position: relative;
  z-index: 2;
}

.music-wave {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 3px;
  z-index: 1;
}

.music-wave span {
  width: 3px;
  height: 8px;
  background: #e94840;
  border-radius: 2px;
  animation: wave 1.2s ease-in-out infinite;
}

.music-wave span:nth-child(2) {
  animation-delay: 0.1s;
}

.music-wave span:nth-child(3) {
  animation-delay: 0.2s;
}

.music-wave span:nth-child(4) {
  animation-delay: 0.3s;
}

.music-wave span:nth-child(5) {
  animation-delay: 0.4s;
}

@keyframes wave {
  0%, 100% {
    height: 8px;
  }
  50% {
    height: 16px;
  }
}

/* 非播放状态时隐藏波形 */
.music-player:not(.playing) .music-wave {
  display: none;
}

/* 响应式设计 */
@media (max-width: 600px) {
  .music-player {
    width: 50px;
    height: 50px;
    top: 15px;
    right: 15px;
  }
  
  .music-icon svg {
    width: 20px;
    height: 20px;
  }
}
</style>