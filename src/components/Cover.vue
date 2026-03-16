<template>
  <div ref="coverElement" class="cover">
    <!-- 艺术文字装饰 -->
    <div class="art-text">
      <div class="chinese-art">婚礼</div>
      <div class="english-art">WEDDING</div>
    </div>

    <div class="cover-content">
      <h1 class="title"></h1>
      <div class="names">
        <span class="groom">{{ groomName }}</span>
        <span class="heart">❤️</span>
        <span class="bride">{{ brideName }}</span>
      </div>
      <div class="wedding-date">
        {{ weddingDate }}
      </div>
      <button class="open-btn" @click="handleAcceptInvitation"><span>接受邀请</span></button>

      <!-- 姓名输入模态框 -->
      <div class="name-input-modal" v-if="showNameInput">
        <div class="modal-content">
          <h3>请输入您的姓名</h3>
          <input type="text" v-model="inputName" placeholder="请输入姓名" @keyup.enter="confirmName">
          <div v-if="errorMessage" class="error-message">{{ errorMessage }}</div>
          <div class="modal-buttons">
            <button @click="confirmName" class="confirm-btn">确认</button>
            <button @click="cancelInput" class="cancel-btn">取消</button>
          </div>
        </div>
      </div>
    </div>

    <!-- 底部标签 -->
    <div class="wedding-tag">
      <span>盼婚礼佳期，与君再相见</span>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue'
import { useRouter } from 'vue-router'

const props = defineProps({
  weddingDate: String,
  groomName: String,
  brideName: String
})

const emit = defineEmits(['openInvitation'])

const router = useRouter()
const coverElement = ref(null)
const showNameInput = ref(false)
const inputName = ref('')
const errorMessage = ref('')

/**
 * 处理接受邀请
 */
const handleAcceptInvitation = () => {
  showNameInput.value = true
  errorMessage.value = ''
}

/**
 * 确认姓名输入
 */
const confirmName = () => {
  if (inputName.value.trim() === '') {
    errorMessage.value = '姓名不能为空！'
    return
  }

  if (inputName.value === props.groomName || inputName.value === props.brideName) {
    router.push('/game')
  } else {
    emit('openInvitation')
  }
  showNameInput.value = false
  inputName.value = ''
  errorMessage.value = ''
}

/**
 * 取消姓名输入
 */
const cancelInput = () => {
  showNameInput.value = false
  inputName.value = ''
  errorMessage.value = ''
}

// 生命周期钩子
onMounted(async () => {
  await nextTick()
  // 移除了setCoverHeight函数，使用CSS的height: 100vh更现代和响应式
})

onUnmounted(() => {
  // 移除了resize事件监听器
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
/* CSS变量定义 */

.cover {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background-image: url('@/assets/images/BG.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  padding: 0 20px;
}

.cover::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(248, 244, 244, 0.3);
  z-index: 1;
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
  color: #e94840;
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

.cover-content {
  position: relative;
  z-index: 2;
  text-align: center;
  color: var(--secondary-color);
  animation: fadeIn 1s ease-in-out;
  max-width: 600px;
  width: 100%;
}

.title {
  font-size: 3em;
  color: #ffffff;
  margin-bottom: 30px;
  font-weight: bold;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.names {
  font-size: 1.8em;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

.groom {
  color: #f3a9a5;
  font-weight: bold;
  font-family: 'STKaiti', 'KaiTi', serif;
  font-size: 1.6em;
}

.bride {
  color: #f3a9a5;
  font-weight: bold;
  font-family: 'STKaiti', 'KaiTi', serif;
  font-size: 1.6em;
}

.heart {
  color: var(--primary-color);
  animation: pulse 1.5s infinite;
  font-size: 1.2em;
}

.wedding-date {
  font-size: 1.2em;
  color: rgba(244, 12, 12, 0.45);
  margin-bottom: 40px;
  font-weight: bold;
}

.open-btn {
  padding: 18px 45px;
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

.open-btn:hover {
  transform: scale(1.05) rotate(-2deg);
  box-shadow: 0 6px 16px rgba(233, 72, 64, 0.4);
  /* background: linear-gradient(135deg, #d43830 0%, #e94840 100%); */
}

.open-btn span {
  position: relative;
  z-index: 2;
  display: block;
}

/* 姓名输入模态框 */
.name-input-modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  background: white;
  padding: 30px;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  width: 90%;
  max-width: 400px;
  animation: slideIn 0.3s ease-out;
}

.modal-content h3 {
  color: var(--secondary-color);
  margin-bottom: 20px;
  text-align: center;
  font-size: 18px;
  font-weight: bold;
}

.modal-content input {
  width: 100%;
  padding: 12px;
  border: 2px solid #eee;
  border-radius: 8px;
  font-size: 16px;
  margin-bottom: 15px;
  transition: border-color 0.3s;
  box-sizing: border-box;
}

.modal-content input:focus {
  outline: none;
  border-color: var(--primary-color);
}

.error-message {
  color: var(--primary-color);
  font-size: 14px;
  margin-bottom: 15px;
  text-align: center;
}

.modal-buttons {
  display: flex;
  gap: 10px;
  justify-content: flex-end;
}

.modal-buttons button {
  padding: 10px 20px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.2s ease;
}

.confirm-btn {
  background: var(--primary-color);
  color: white;
}

.cancel-btn {
  background: #f0f0f0;
  color: #666;
}

.modal-buttons button:hover {
  transform: scale(1.05);
}

/* 底部标签 */
.wedding-tag {
  position: absolute;
  bottom: 40px;
  right: 40px;
  color: rgb(228, 129, 129);
  padding: 10px 20px;
  border-radius: 20px;
  font-size: 16px;
  font-weight: bold;
}

/* 动画效果 */
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

@keyframes pulse {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.2);
  }

  100% {
    transform: scale(1);
  }
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
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

  .cover {
    padding: 0 15px;
  }

  .cover-content {
    padding: 0 10px;
  }

  .title {
    font-size: 2.2em;
    margin-bottom: 20px;
  }

  .names {
    font-size: 1.4em;
    margin-bottom: 15px;
    gap: 15px;
  }

  .wedding-date {
    font-size: 1em;
    margin-bottom: 30px;
  }

  .open-btn {
    padding: 12px 30px;
    font-size: 1.1em;
  }

  .wedding-tag {
    bottom: 20px;
    right: 20px;
    padding: 8px 16px;
    font-size: 14px;
  }

  .modal-content {
    padding: 25px;
    width: 85%;
  }

  .modal-content h3 {
    font-size: 16px;
  }

  .modal-content input {
    padding: 10px;
    font-size: 14px;
  }

  .modal-buttons button {
    padding: 8px 16px;
    font-size: 13px;
  }
}
</style>
