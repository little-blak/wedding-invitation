<template>
  <div class="invitation-container">
    <!-- 封面区域 -->
    <section class="cover-section">
      <div class="art-text">
        <!-- 切图替换 -->
        <div class="chinese-art">好久不见</div>
        <div class="english-art">LONG TIME NO SEE</div>
      </div>
      <div class="top-msg">
        <p>wellcome our wedding</p>
        <p>bleano gerio gjieor gio</p>
      </div>
      <div class="couple-photo">
        <img :src="couplePhoto" alt="新人照片">
      </div>
      <div class="wedding-tag">
        <span>我们婚礼见</span>
      </div>
    </section>

    <!-- 邀请信息区域 -->
    <section class="invitation-section">
      <div class="couple-names">
        {{ groomName }} ❤️ {{ brideName }}
      </div>
      <div class="wedding-description">
        <p>
          协同我们的父母
          <br>
          Together with our parents
        </p>
        <p>
          真诚地邀请您
          <br>
          We sincerely invite you to
        </p>
        <p>
          出席我们的新婚喜宴
          <br>
          Attend our wedding reception
        </p>
      </div>

      <div class="wedding-photo">
        <img :src="weddingPhoto" alt="婚礼照片">
      </div>
    </section>
      <div class="wedding-date">
        {{ weddingDate }}我们要结婚啦！💓💓💓
      </div>
      
      <!-- 倒计时组件 -->
      <Countdown 
        :weddingDate="weddingDate" 
        :weddingTime="weddingTime"
      />
      
      <div class="invitation-text">
        诚邀您出席我们的婚礼
      </div>
    <!-- 照片布局区域 -->
    <section class="photos-section">
      <!-- 第一张照片 -->
      <div class="photo-item full-width">
        <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=elegant%20wedding%20photo%20of%20couple%20in%20formal%20attire%2C%20white%20background%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照1">
      </div>
      
      <!-- 邀请函内容 -->
      <div class="invitation-content">
        <div class="invitation-header">
          <div class="header-left">相爱</div>
          <div class="header-line"></div>
          <div class="header-right">相守</div>
        </div>
        
        <div class="invitation-body">
          <div class="body-left">
            <div class="invitation-title">INVITATION</div>
          </div>
          <div class="body-center">
            <div class="double-happiness">囍</div>
          </div>
          
          <div class="body-right">
            <div class="invitation-text">
              <p>我们一起开始这段旅程</p>
              <p>两颗心跳动如一</p>
              <p>我们面对前方的路</p>
              <p>以爱作为我们的指南</p>
              <p>我们可能会跌倒，可能会摔倒</p>
              <p>但我们会站起来，</p>
              <p>继续前行因为这段旅程值得我们付出</p>
              <p>当我们在一起，手牵着手</p>
            </div>
          </div>
        </div>
      </div>
      
      <!-- 两张照片并排 -->
      <!-- 垂直排列的照片 -->
      <div class="vertical-photos">
        <div class="photo-item">
          <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20outdoor%20wedding%20photo%2C%20natural%20light%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照2">
        </div>
        <div class="photo-item">
          <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20in%20white%20wedding%20dress%2C%20groom%20in%20black%20suit%2C%20romantic%20pose%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照3">
        </div>
      </div>
      
      <!-- 爱情宣言 -->
      <div class="love-message">
        <p>茫茫人海，能够遇见就是一种缘分</p>
        <p>更何况我们相识、相知</p>
        <p>没有委曲求全，只有顺其自然</p>
        <p>和恰到好处</p>
        <p class="english-message">You make my heart smile</p>
        <p class="love-title">LOVE</p>
      </div>
      

      <!-- 更多照片 -->
      <div class="photo-grid three-col">
        <div class="photo-item">
          <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=couple%20in%20wedding%20attire%2C%20garden%20setting%2C%20romantic%20moment%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照4">
        </div>
        <div class="photo-item">
          <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20holding%20hands%2C%20sunset%2C%20romantic%20lighting%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照5">
        </div>
      </div>
      
      <!-- 爱情宣言 -->
      <div class="love-declaration">
        <p class="declaration-title">岁月漫长</p>
        <p>我跨过山海义无反顾奔向你</p>
        <p>而你也在披荆斩棘为我而来</p>
        <p class="english-declaration">For you, a thousand times over</p>
      </div>
      
      <div class="photo-item full-width">
        <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=couple%20walking%20down%20aisle%2C%20wedding%20ceremony%2C%20emotional%20moment%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照7">
      </div>
      <!-- 相知相伴部分 -->
      <div class="knowing-accompanying">
        <div class="section-header">
          <div class="header-left">相知</div>
          <div class="header-line"></div>
          <div class="header-right">相伴</div>
        </div>
        
        <div class="double-happiness-center">囍</div>
        
        <div class="accompanying-text">
          <p>热爱彼此，包容彼此，信任彼此</p>
          <p>在快乐的日子里共同举杯</p>
          <p>在难过的日子里伸出怀抱</p>
          <p class="english-text">Brief is life but love is long</p>
        </div>
        
        <div class="final-photos">
          <div class="photo-item">
            <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=green%20tree%20leaves%2C%20natural%20background%2C%20fresh%20and%20vibrant&image_size=portrait_4_3" alt="绿树">
          </div>
          <div class="photo-item">
            <img src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20in%20wedding%20attire%2C%20outdoor%20garden%20setting%2C%20happy%20moment%2C%20professional%20photography&image_size=portrait_4_3" alt="婚纱照">
          </div>
        </div>
      </div>
      <!-- 婚礼详情 -->
      <div class="wedding-details">
        <div class="wedding-message">
          <p>答案很长，我得用一生去回答你</p>
          <p>准备好听我说了吗？</p>
        </div>
        
        <div class="wedding-double-happiness">囍</div>
        
        <div class="wedding-invitation">INVITATION</div>
        
        <div class="wedding-info">
          <div class="info-left">
            <p>2026年4月12日 星期日</p>
            <p>农历四月廿二 12:00PM</p>
          </div>
          <div class="info-divider"></div>
          <div class="info-right">
            <p>许村镇茗山村</p>
            <p>10组16号</p>
          </div>
        </div>
      </div>
      

      
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Countdown from './Countdown.vue'

const props = defineProps({
  groomName: {
    type: String,
    default: '王超强'
  },
  brideName: {
    type: String,
    default: '安亚成'
  },
  weddingDate: {
    type: String,
  },
  weddingTime: {
    type: String,
  },
  couplePhoto: {
    type: String,
    default: 'https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=elegant%20wedding%20photo%20of%20couple%20in%20formal%20attire%2C%20white%20background%2C%20professional%20photography&image_size=portrait_4_3'
  },
  weddingPhoto: {
    type: String,
    default: 'https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=happy%20couple%20at%20wedding%2C%20bride%20in%20white%20dress%2C%20groom%20in%20black%20suit%2C%20outdoor%20setting%2C%20professional%20photography&image_size=portrait_4_3'
  }
})
</script>

<style scoped>
.invitation-container {
  font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif;
  background: #ffffff;
  max-width: 800px;
  margin: 0 auto;
  position: relative;
}

/* 封面区域 */
.cover-section {
  position: relative;
  padding: 40px 20px;
  text-align: center;
  background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%);
}
.cover-section .top-msg {
  font-size: 14px;
  text-align: right;
  color: #c95555;
  margin-bottom: 36px;
}

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
  color: #333;
  letter-spacing: 2px;
}

.couple-photo {
  margin: 60px 0 20px;
}

.couple-photo img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

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

/* 邀请信息区域 */
.invitation-section {
  padding: 40px 20px;
  text-align: center;
  background: #ffffff;
  color: #333;
}
.invitation-section .wedding-description {
  color: #999999;
  text-align: left;
  margin: 48px 0;
  margin-left: 15%;
}

.invitation-section .wedding-description p {
  margin-bottom: 16px;
}

.couple-names {
  font-size: 32px;
  font-weight: bold;
  color: #333;
  margin-bottom: 15px;
}

.wedding-date {
  font-size: 20px;
  color: #333;
  font-weight: bold;
  text-align: center;
  margin-bottom: 24px;
}

.wedding-title {
  font-size: 24px;
  font-weight: bold;
  color: #e94840;
  margin-bottom: 30px;
}

/* 倒计时样式 */
.countdown {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin: 30px 0;
}

.countdown-item {
  width: 80px;
  height: 80px;
  border: 2px solid #e94840;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: #ffffff;
}

.countdown-number {
  font-size: 24px;
  font-weight: bold;
  color: #e94840;
}

.countdown-label {
  font-size: 14px;
  color: #666;
  margin-top: 5px;
}

.invitation-text {
  font-size: 18px;
  color: #666;
  margin: 30px 0;
  line-height: 1.4;
}

.wedding-photo {
  margin-top: 20px;
}

.wedding-photo img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

/* 照片布局区域 */
.photos-section {
  padding: 40px 20px;
  background: #ffffff;
  border-top: 1px solid #f0f0f0;
}

.photo-item {
  margin-bottom: 20px;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.photo-item:hover {
  transform: scale(1.02);
}

.photo-item img {
  width: 100%;
  height: auto;
  display: block;
}

.photo-item.full-width {
  width: 100%;
}

.photo-grid {
  display: grid;
  gap: 15px;
  margin-bottom: 20px;
}

.photo-grid.two-col {
  grid-template-columns: repeat(2, 1fr);
}

.photo-grid.three-col {
  grid-template-columns: repeat(3, 1fr);
}

/* 垂直排列照片样式 */
.vertical-photos {
  display: flex;
  flex-direction: column;
  gap: 40px;
  margin: 40px 0;
}

.vertical-photos .photo-item {
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  max-width: 80%;
}

/* 第一个照片左边留白 */
.vertical-photos .photo-item:nth-child(1) {
  align-self: flex-start;
  margin-left: 0;
}

/* 第二个照片右边留白 */
.vertical-photos .photo-item:nth-child(2) {
  align-self: flex-end;
  margin-right: 0;
}

.vertical-photos .photo-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.vertical-photos .photo-item img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.3s ease;
}

.vertical-photos .photo-item:hover img {
  transform: scale(1.05);
}

/* 爱情宣言样式 */
.love-message {
  padding: 60px 20px;
  background: #f9f9f9;
  margin: 40px 0;
  border-radius: 10px;
  text-align: center;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.love-message p {
  font-size: 18px;
  color: #333;
  margin-bottom: 20px;
  line-height: 1.6;
}

.love-message .english-message {
  font-size: 16px;
  color: #666;
  font-style: italic;
  margin-top: 30px;
  margin-bottom: 40px;
}

.love-message .love-title {
  font-size: 36px;
  font-weight: bold;
  color: var(--primary-color);
  margin-top: 20px;
}

/* 爱情宣言样式 */
.love-declaration {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  text-align: center;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.love-declaration .declaration-title {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 30px;
}

.love-declaration p {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
  line-height: 1.6;
}

.love-declaration .english-declaration {
  font-size: 14px;
  color: #999;
  font-style: italic;
  margin-top: 30px;
}

/* 相知相伴部分样式 */
.knowing-accompanying {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  text-align: center;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.section-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
}

.section-header .header-left,
.section-header .header-right {
  font-size: 24px;
  font-weight: bold;
  color: var(--primary-color);
}

.section-header .header-line {
  flex: 1;
  height: 1px;
  background: #e0e0e0;
  margin: 0 20px;
}

.double-happiness-center {
  font-size: 80px;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
  margin: 40px 0;
}

.accompanying-text {
  margin-bottom: 40px;
}

.accompanying-text p {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
  line-height: 1.6;
}

.accompanying-text .english-text {
  font-size: 14px;
  color: #999;
  font-style: italic;
  margin-top: 30px;
}

.final-photos {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-top: 40px;
}

.final-photos .photo-item {
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.final-photos .photo-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.final-photos .photo-item img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.3s ease;
}

.final-photos .photo-item:hover img {
  transform: scale(1.05);
}

.wedding-details {
  background: #ffffff;
  padding: 60px 20px;
  border-radius: 10px;
  margin: 40px 0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.wedding-message {
  margin-bottom: 40px;
}

.wedding-message p {
  font-size: 18px;
  color: #333;
  margin-bottom: 20px;
  line-height: 1.6;
}

.wedding-double-happiness {
  font-size: 80px;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
  margin: 40px 0;
}

.wedding-invitation {
  font-size: 24px;
  font-weight: bold;
  color: var(--primary-color);
  letter-spacing: 5px;
  margin: 40px 0;
}

.wedding-info {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 40px;
  gap: 40px;
}

.info-left,
.info-right {
  text-align: left;
  font-size: 16px;
  color: #666;
}

.info-left p,
.info-right p {
  margin-bottom: 10px;
  line-height: 1.6;
}

.info-divider {
  width: 1px;
  height: 80px;
  background: #e0e0e0;
}

/* 响应式设计 */
@media (max-width: 600px) {
  .wedding-details {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .wedding-message p {
    font-size: 16px;
    margin-bottom: 15px;
  }

  .wedding-double-happiness {
    font-size: 60px;
    margin: 30px 0;
  }

  .wedding-invitation {
    font-size: 20px;
    margin: 30px 0;
  }

  .wedding-info {
    flex-direction: column;
    gap: 20px;
    margin-top: 30px;
  }

  .info-left,
  .info-right {
    text-align: center;
    font-size: 14px;
  }

  .info-divider {
    width: 80px;
    height: 1px;
  }
}

/* 邀请函内容样式 */
.invitation-content {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.invitation-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
}

.header-left,
.header-right {
  font-size: 24px;
  font-weight: bold;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
}

.header-line {
  flex: 1;
  height: 1px;
  background: #e0e0e0;
  margin: 0 20px;
}

.invitation-body {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 40px;
  align-items: center;
}

.body-left {
  text-align: center;
}

.sincere-invitation {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
  font-style: italic;
}

.invitation-title {
  font-size: 28px;
  font-weight: bold;
  color: var(--primary-color);
  line-height: 1.2;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.body-center {
  text-align: center;
}

.double-happiness {
  font-size: 80px;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
}

.body-right {
  text-align: left;
}

.invitation-text p {
  font-size: 14px;
  color: #666;
  margin-bottom: 10px;
  line-height: 1.6;
  font-family: 'STKaiti', 'KaiTi', serif;
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

  .cover-section {
    padding: 20px;
  }

  .couple-photo {
    margin: 40px 0 20px;
  }

  .wedding-tag {
    bottom: 20px;
    right: 20px;
    padding: 8px 16px;
    font-size: 14px;
  }

  .invitation-section {
    padding: 30px 20px;
  }

  .couple-names {
    font-size: 24px;
  }

  .parents-info,
  .invitation-text,
  .wedding-event {
    font-size: 16px;
  }

  .photos-section {
    padding: 20px;
  }

  .photo-grid.two-col {
    grid-template-columns: 1fr;
  }

  .photo-grid.three-col {
    grid-template-columns: repeat(2, 1fr);
  }

  .wedding-details {
    padding: 15px;
  }

  .wedding-details .detail-item {
    flex-direction: column;
    align-items: flex-start;
    gap: 5px;
  }

  .interaction-buttons {
    gap: 5px;
  }

  .action-buttons {
    flex-direction: column;
    align-items: center;
  }

  .action-btn {
    width: 80%;
    text-align: center;
  }

  /* 邀请函内容响应式 */
  .invitation-content {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .invitation-header {
    margin-bottom: 30px;
  }

  .header-left,
  .header-right {
    font-size: 20px;
  }

  .invitation-body {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .body-left,
  .body-right {
    text-align: center;
  }

  .invitation-title {
    font-size: 24px;
  }

  .double-happiness {
    font-size: 60px;
  }

  .invitation-text p {
    font-size: 13px;
  }

  /* 爱情宣言响应式 */
  .love-message {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .love-message p {
    font-size: 16px;
    margin-bottom: 15px;
  }

  .love-message .english-message {
    font-size: 14px;
    margin-top: 20px;
    margin-bottom: 30px;
  }

  .love-message .love-title {
    font-size: 28px;
  }

  /* 爱情宣言响应式 */
  .love-declaration {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .love-declaration .declaration-title {
    font-size: 20px;
    margin-bottom: 20px;
  }

  .love-declaration p {
    font-size: 14px;
    margin-bottom: 15px;
  }

  .love-declaration .english-declaration {
    font-size: 12px;
    margin-top: 20px;
  }

  /* 相知相伴部分响应式 */
  .knowing-accompanying {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .section-header {
    margin-bottom: 30px;
  }

  .section-header .header-left,
  .section-header .header-right {
    font-size: 20px;
  }

  .double-happiness-center {
    font-size: 60px;
    margin: 30px 0;
  }

  .accompanying-text p {
    font-size: 14px;
    margin-bottom: 15px;
  }

  .accompanying-text .english-text {
    font-size: 12px;
    margin-top: 20px;
  }

  .final-photos {
    grid-template-columns: 1fr;
    gap: 15px;
    margin-top: 30px;
  }
}
</style>