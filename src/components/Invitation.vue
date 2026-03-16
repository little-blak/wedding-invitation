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
        <p>with all our love</p>
        <p>we invite you to witness</p>
        <p>the union of our hearts in marriage</p>
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
    <Countdown :weddingDate="weddingDate" :weddingTime="weddingTime" />

    <div class="invitation-text">
      诚邀您出席我们的婚礼
    </div>
    <!-- 照片布局区域 -->
    <section class="photos-section">
      <!-- 第一张照片 -->
      <div class="photo-item full-width">
        <img
          src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=elegant%20wedding%20photo%20of%20couple%20in%20formal%20attire%2C%20white%20background%2C%20professional%20photography&image_size=portrait_4_3"
          alt="婚纱照1">
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
          <img
            src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20outdoor%20wedding%20photo%2C%20natural%20light%2C%20professional%20photography&image_size=portrait_4_3"
            alt="婚纱照2">
        </div>
        <div class="photo-item">
          <img
            src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20in%20white%20wedding%20dress%2C%20groom%20in%20black%20suit%2C%20romantic%20pose%2C%20professional%20photography&image_size=portrait_4_3"
            alt="婚纱照3">
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
          <img
            src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=couple%20in%20wedding%20attire%2C%20garden%20setting%2C%20romantic%20moment%2C%20professional%20photography&image_size=portrait_4_3"
            alt="婚纱照4">
        </div>
        <div class="photo-item">
          <img
            src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20holding%20hands%2C%20sunset%2C%20romantic%20lighting%2C%20professional%20photography&image_size=portrait_4_3"
            alt="婚纱照5">
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
        <img
          src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=couple%20walking%20down%20aisle%2C%20wedding%20ceremony%2C%20emotional%20moment%2C%20professional%20photography&image_size=portrait_4_3"
          alt="婚纱照7">
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
            <img src="@/assets/images/ZS1.jpg">
          </div>
          <div class="photo-item">
            <img
              src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20in%20wedding%20attire%2C%20outdoor%20garden%20setting%2C%20happy%20moment%2C%20professional%20photography&image_size=portrait_4_3"
              alt="婚纱照">
          </div>
        </div>
      </div>

      <!-- 双向奔赴的爱情 -->
      <div class="just-married-section">
        <div class="just-married-header">
          <h2>JUST MARRIED</h2>
        </div>

        <div class="love-declaration-text">
          <p>双向奔赴的爱情，信守彼此的约定</p>
          <p>始于初见，止于终老</p>
          <p>余生有你，何其欢喜</p>
          <p class="english-text">You complete me</p>
        </div>

        <div class="couple-photo-section">
          <div class="photo-container">
            <img
              src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20in%20traditional%20chinese%20wedding%20attire%2C%20bride%20in%20red%20dress%2C%20groom%20in%20brown%20suit%2C%20holding%20traditional%20chinese%20wedding%20dolls%2C%20indoor%20setting%2C%20professional%20photography&image_size=portrait_4_3"
              alt="传统婚纱照">
          </div>
          <div class="side-text">
            <p>遇到你是故事的开始</p>
            <p>走到底是人间的欢喜</p>
          </div>
        </div>
      </div>

      <!-- My Heart Is With You 部分 -->
      <div class="heart-with-you-section">
        <div class="heart-header">
          <h2>MY HEART IS WITH YOU</h2>
          <p class="english-text">For the same reason you love me</p>
          <p class="english-text">I love you, too</p>
        </div>

        <div class="heart-photos">
          <div class="heart-photo-item">
            <img
              src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20leaning%20on%20wooden%20railing%2C%20bride%20in%20red%20traditional%20dress%2C%20groom%20in%20brown%20suit%2C%20indoor%20setting%2C%20professional%20photography&image_size=landscape_4_3"
              alt="婚纱照1">
          </div>
          <div class="heart-photo-item">
            <img
              src="https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=bride%20and%20groom%20facing%20each%20other%2C%20bride%20in%20red%20traditional%20dress%2C%20groom%20in%20brown%20suit%2C%20indoor%20setting%2C%20professional%20photography&image_size=landscape_4_3"
              alt="婚纱照2">
          </div>
        </div>

        <div class="heart-decoration">
          <div class="heart-icon"></div>
          <div class="heart-icon small"></div>
          <div class="double-happiness-icon">囍</div>
        </div>
      </div>

      <!-- 往后余生部分 -->
      <div class="rest-of-life-section">
        <div class="rest-of-life-header">
          <p class="main-text">往后余生，四季与你</p>
          <p class="sub-text">我们牵手从天光乍破到暮雪白头</p>
          <p class="english-text">Love without end hath no end</p>
        </div>

        <div class="rest-of-life-photo">
          <img src="@/assets/images/ZS1.jpg" alt="比心婚纱照">
          <div class="calendar-badge">
            <div class="calendar-header">
              <div class="year">2026</div>
              <div class="month">4月</div>
            </div>
            <div class="calendar-weekdays">
              <span>一</span>
              <span>二</span>
              <span>三</span>
              <span>四</span>
              <span>五</span>
              <span>六</span>
              <span>日</span>
            </div>
            <div class="calendar-days">
              <span>30</span>
              <span>31</span>
              <span>1</span>
              <span>2</span>
              <span>3</span>
              <span>4</span>
              <span>5</span>
              <span>6</span>
              <span>7</span>
              <span>8</span>
              <span>9</span>
              <span>10</span>
              <span>11</span>
              <span class="special-day">12</span>
              <span>13</span>
              <span>14</span>
              <span>15</span>
              <span>16</span>
              <span>17</span>
              <span>18</span>
              <span>19</span>
              <span>20</span>
              <span>21</span>
              <span>22</span>
              <span>23</span>
              <span>24</span>
              <span>25</span>
              <span>26</span>
              <span>27</span>
              <span>28</span>
              <span>29</span>
              <span>30</span>
            </div>
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

    <!-- 地图组件 -->
    <section class="map-section">
      <MapComponent 
        :latitude="30.471638" 
        :longitude="120.407505" 
        locationName="XX酒店XX厅"
        address="浙江省杭州市西湖区"
      />
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Countdown from './Countdown.vue'
import MapComponent from './MapComponent.vue'

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
    default: 'src/assets/images/QMZS2.jpg'
  },
  weddingPhoto: {
    type: String,
    default: 'src/assets/images/QMZS4.jpg'
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
  bottom: 16px;
  right: 20px;
  color: rgba(0, 0, 0, 0.65);
  font-size: 18px;
  font-weight: bold;
  width: 100px;
  height: 24px;
  border-right: 1px solid transparent;
  animation: typing 4.5s steps(20, end) infinite, blink-caret .75s step-end infinite;
  word-break: break-all;
  overflow: hidden;
}

/* 打印效果 */
@keyframes typing {

  0%,
  100% {
    width: 0;
  }

  50% {
    width: 100px;
  }
}

/* 光标 */
@keyframes blink-caret {

  from,
  to {
    border-color: transparent;
  }

  50% {
    border-color: currentColor;
  }
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

/* 双向奔赴的爱情部分样式 */
.just-married-section {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.just-married-header {
  text-align: center;
  margin-bottom: 40px;
}

.just-married-header h2 {
  font-size: 32px;
  font-weight: bold;
  color: var(--primary-color);
  letter-spacing: 5px;
}

.love-declaration-text {
  text-align: center;
  margin-bottom: 40px;
}

.love-declaration-text p {
  font-size: 18px;
  color: #333;
  margin-bottom: 20px;
  line-height: 1.6;
}

.love-declaration-text .english-text {
  font-size: 16px;
  color: #999;
  font-style: italic;
  margin-top: 30px;
}

.couple-photo-section {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 40px;
  gap: 20px;
}

.photo-container {
  flex: 1;
  max-width: 70%;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.photo-container:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.photo-container img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.3s ease;
}

.photo-container:hover img {
  transform: scale(1.05);
}

.side-text {
  flex-shrink: 0;
  writing-mode: vertical-rl;
  text-orientation: mixed;
  font-size: 18px;
  color: #666;
  font-weight: bold;
  letter-spacing: 3px;
  line-height: 2.5;
  text-align: center;
  padding: 20px 0;
}

/* My Heart Is With You 部分样式 */
.heart-with-you-section {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  font-family: 'STKaiti', 'KaiTi', serif;
  position: relative;
  overflow: hidden;
}

.heart-header {
  text-align: center;
  margin-bottom: 40px;
}

.heart-header h2 {
  font-size: 32px;
  font-weight: bold;
  color: var(--primary-color);
  letter-spacing: 5px;
  margin-bottom: 20px;
}

.heart-header .english-text {
  font-size: 16px;
  color: #999;
  font-style: italic;
  margin-bottom: 10px;
}

.heart-photos {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-top: 40px;
  position: relative;
  z-index: 1;
  margin-left: 80px;
}

.heart-photo-item {
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.heart-photo-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.heart-photo-item img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.3s ease;
}

.heart-photo-item:hover img {
  transform: scale(1.05);
}

.heart-decoration {
  position: absolute;
  left: 20px;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  z-index: 0;
}

.heart-icon {
  width: 30px;
  height: 30px;
  background: var(--primary-color);
  transform: rotate(45deg);
  position: relative;
}

.heart-icon::before,
.heart-icon::after {
  content: '';
  position: absolute;
  width: 30px;
  height: 30px;
  background: var(--primary-color);
  border-radius: 50%;
}

.heart-icon::before {
  top: -15px;
  left: 0;
}

.heart-icon::after {
  top: 0;
  left: -15px;
}

.heart-icon.small {
  width: 20px;
  height: 20px;
}

.heart-icon.small::before,
.heart-icon.small::after {
  width: 20px;
  height: 20px;
}

.heart-icon.small::before {
  top: -10px;
}

.heart-icon.small::after {
  left: -10px;
}

.double-happiness-icon {
  font-size: 40px;
  color: var(--primary-color);
  font-family: 'STKaiti', 'KaiTi', serif;
  margin-top: 20px;
}

/* 往后余生部分样式 */
.rest-of-life-section {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
  font-family: 'STKaiti', 'KaiTi', serif;
  text-align: center;
}

.rest-of-life-header {
  margin-bottom: 40px;
}

.rest-of-life-header .main-text {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 15px;
}

.rest-of-life-header .sub-text {
  font-size: 18px;
  color: #666;
  margin-bottom: 20px;
  line-height: 1.6;
}

.rest-of-life-header .english-text {
  font-size: 16px;
  color: #999;
  font-style: italic;
  margin-top: 10px;
}

.rest-of-life-photo {
  position: relative;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  max-width: 80%;
  margin: 0 auto;
}

.rest-of-life-photo:hover {
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.rest-of-life-photo img {
  width: 100%;
  height: auto;
  display: block;
}

.calendar-badge {
  position: absolute;
  bottom: 20px;
  left: 20px;
  right: 20px;
  background: rgba(255, 255, 255, 0.15);
  /* color: var(--primary-color);
  border: 2px solid var(--primary-color); */
  color: rgba(255, 255, 255, 0.85);
  border: 2px solid rgba(255, 255, 255, 0.85);
  border-radius: 6px;
  padding: 16px;
  z-index: 1;
  font-family: 'STKaiti', 'KaiTi', serif;
}

.calendar-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.calendar-header .year {
  font-size: 24px;
  font-weight: bold;
}

.calendar-header .month {
  font-size: 24px;
  font-weight: bold;
}

.calendar-weekdays {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 5px;
  margin-bottom: 10px;
  text-align: center;
  font-size: 14px;
  font-weight: bold;
}

.calendar-days {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 5px;
  text-align: center;
  font-size: 14px;
}

.calendar-days span {
  padding: 5px 0;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.calendar-days .special-day {
  background: var(--primary-color);
  color: white;
  font-weight: bold;
  position: relative;
}

.calendar-days .special-day::before {
  content: '❤';
  position: absolute;
  top: -10px;
  right: 5px;
  font-size: 12px;
  color: var(--primary-color);
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

  /* 双向奔赴的爱情部分响应式 */
  .just-married-section {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .just-married-header h2 {
    font-size: 24px;
  }

  .love-declaration-text p {
    font-size: 16px;
    margin-bottom: 15px;
  }

  .love-declaration-text .english-text {
    font-size: 14px;
    margin-top: 20px;
  }

  .couple-photo-section {
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }

  .side-text {
    writing-mode: horizontal-tb;
    text-orientation: mixed;
    text-align: center;
    margin-top: 20px;
  }

  /* My Heart Is With You 部分响应式 */
  .heart-with-you-section {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .heart-header h2 {
    font-size: 24px;
  }

  .heart-header .english-text {
    font-size: 14px;
  }

  .heart-photos {
    margin-left: 0;
  }

  .heart-decoration {
    position: relative;
    left: 0;
    top: 0;
    transform: none;
    flex-direction: row;
    justify-content: center;
    margin-bottom: 30px;
  }

  .double-happiness-icon {
    font-size: 30px;
  }

  /* 往后余生部分响应式 */
  .rest-of-life-section {
    padding: 40px 15px;
    margin: 30px 0;
  }

  .rest-of-life-header .main-text {
    font-size: 20px;
  }

  .rest-of-life-header .sub-text {
    font-size: 16px;
  }

  .rest-of-life-header .english-text {
    font-size: 14px;
  }

  .rest-of-life-photo {
    max-width: 100%;
  }

  .calendar-badge {
    padding: 10px;
  }

  .calendar-header .year,
  .calendar-header .month {
    font-size: 20px;
  }

  .calendar-weekdays,
  .calendar-days {
    font-size: 12px;
  }

  .calendar-days span {
    padding: 3px 0;
  }
}

/* 邀请函内容样式 */
.invitation-content {
  padding: 60px 20px;
  background: #ffffff;
  margin: 40px 0;
  border-radius: 10px;
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
  
  /* 地图组件响应式 */
  .map-section {
    padding: 20px;
  }
  
  .map-container {
    margin: 0 auto;
    max-width: 90%;
  }
  
  .map-placeholder {
    padding: 30px 20px;
  }
  
  .map-icon {
    font-size: 30px;
  }
  
  .map-title {
    font-size: 16px;
  }
  
  .map-subtitle {
    font-size: 12px;
  }
}

/* 地图组件样式 */
.map-section {
  padding: 40px 20px;
  background: #ffffff;
  border-top: 1px solid #f0f0f0;
  text-align: center;
}

.map-section h3 {
  color: var(--primary-color, #e94840);
  margin-bottom: 20px;
  font-size: 20px;
  font-weight: bold;
}

.map-container {
  margin: 0 auto;
  max-width: 600px;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: transform 0.3s;
}

.map-container:hover {
  transform: scale(1.02);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
}

.map-placeholder {
  background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%);
  padding: 50px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.map-icon {
  font-size: 48px;
  color: var(--primary-color, #e94840);
}

.map-info {
  text-align: center;
}

.map-title {
  font-size: 18px;
  font-weight: bold;
  color: #333;
  margin-bottom: 5px;
}

.map-subtitle {
  font-size: 14px;
  color: #666;
  font-style: italic;
}

.map-section {
  padding: 40px 20px;
  background: #ffffff;
  border-top: 1px solid #f0f0f0;
  text-align: center;
}

/* 响应式设计 */
@media (max-width: 600px) {
  .map-section {
    padding: 20px;
  }
}
</style>