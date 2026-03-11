<template>
  <div class="video-container">
    
    <!-- 艺术文字装饰 -->
    <div class="art-text">
      <div class="chinese-art">婚礼</div>
      <div class="english-art">WEDDING</div>
    </div>
    
    <div class="video-wrapper">
      <video 
        ref="videoPlayer"
        :src="videoSrc" 
        controls 
        autoplay
      ></video>
      <button class="next-button" @click="goToNext">
        <span>进入邀请函</span>
      </button>
    </div>
    
    <!-- 底部标签 -->
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  videoSrc: {
    type: String,
    default: ''
  }
})

const emit = defineEmits(['video-ended'])

const videoPlayer = ref(null)

/**
 * 进入邀请函
 */
const goToNext = () => {
  emit('video-ended')
}

// 确保视频自动播放
onMounted(() => {
  if (videoPlayer.value) {
    videoPlayer.value.play().catch(error => {
      console.error('自动播放失败:', error)
    })
  }
})
</script>

<style>
/* 引入Google Fonts草体字体 */
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap');

:root {
  --primary-color: #e94840;
  --secondary-color: #333;
  --light-gray: #f5f5f5;
  --white: #ffffff;
  --font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif;
  --cursive-font: 'Dancing Script', cursive;
  --border-radius: 10px;
  --box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}
</style>

<style scoped>
.video-container {  
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%);
  z-index: 2000;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  padding: 0 20px;
}

/* 艺术文字装饰 */
.art-text {
  position: absolute;
  top: 40px;
  left: 40px;
  text-align: left;
}

.chinese-art {
  font-size: 48px;
  font-weight: bold;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
  writing-mode: vertical-rl;
  text-orientation: upright;
  margin-bottom: 20px;
}

.english-art {
  font-size: 24px;
  font-weight: 300;
  color: var(--secondary-color);
  letter-spacing: 2px;
}

.video-wrapper {
  position: relative;
  width: 100%;
  max-width: 800px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  z-index: 2;
}

video {
  max-width: 100%;
  max-height: 60vh;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
}

.next-button {
  padding: 5px 5px;
  font-size: 1.3em;
  color: rgb(244, 12, 12);
  border: 1px solid rgb(244, 12, 12);
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(233, 72, 64, 0.3);
  font-family: 'STKaiti', 'KaiTi', serif;
  position: relative;
  overflow: hidden;
  transform: rotate(-2deg);
  letter-spacing: 2px;
  font-weight: bold;
}

.next-button:hover {
  transform: scale(1.05) rotate(-2deg);
  box-shadow: 0 4px 12px rgba(233, 72, 64, 0.3);
}

.next-button span {
  display: block;
  padding: 0 20px;
  line-height: 1.8;
  text-orientation: upright;
}

/* 底部标签 */
.wedding-tag {
  position: absolute;
  bottom: 40px;
  right: 40px;
  background: rgba(233, 72, 64, 0.9);
  color: white;
  padding: 10px 20px;
  border-radius: 20px;
  font-size: 16px;
  font-weight: bold;
}

/* 响应式设计 */
@media (max-width: 600px) {
  .art-text {
    top: 20px;
    left: 20px;
  }

  .chinese-art {
    font-size: 36px;
  }

  .english-art {
    font-size: 18px;
  }

  .video-container {
    padding: 0 15px;
  }

  video {
    max-height: 50vh;
  }

  .next-button {
    font-size: 1em;
    margin-top: 20px;
  }

  .wedding-tag {
    bottom: 20px;
    right: 20px;
    padding: 8px 16px;
    font-size: 14px;
  }
}
</style>
