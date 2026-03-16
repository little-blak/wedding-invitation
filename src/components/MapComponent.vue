<template>
  <div class="map-component">
    <h3>婚礼地点</h3>
    <div ref="mapContainer" class="map-container"></div>
    <div class="map-info">
      <div class="map-title">{{ locationName }}</div>
      <div class="map-address">{{ address }}</div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  /**
   * 纬度
   */
  latitude: {
    type: Number,
    default: 30.471638
  },
  /**
   * 经度
   */
  longitude: {
    type: Number,
    default: 120.407505
  },
  /**
   * 地点名称
   */
  locationName: {
    type: String,
    default: 'XX酒店XX厅'
  },
  /**
   * 详细地址
   */
  address: {
    type: String,
    default: '浙江省杭州市西湖区'
  },
  /**
   * 地图高度
   */
  height: {
    type: String,
    default: '300px'
  }
})

const mapContainer = ref(null)
let map = null
let marker = null

onMounted(() => {
  // 初始化地图
  initMap()
})

onUnmounted(() => {
  // 销毁地图实例
  if (map) {
    map.destroy()
  }
})

const initMap = () => {
  if (!mapContainer.value || !window.AMap) return

  // 创建地图实例
  map = new window.AMap.Map(mapContainer.value, {
    center: [props.longitude, props.latitude],
    zoom: 16,
    resizeEnable: true
  })

  // 添加标记
  marker = new window.AMap.Marker({
    position: [props.longitude, props.latitude],
    title: props.locationName,
    icon: new window.AMap.Icon({
      size: new window.AMap.Size(40, 40),
      image: 'https://a.amap.com/jsapi_demos/static/demo-center/icons/poi-marker-default.png',
      imageSize: new window.AMap.Size(40, 40)
    })
  })

  marker.setMap(map)

  // 添加信息窗口
  const infoWindow = new window.AMap.InfoWindow({
    content: `
      <div style="padding: 10px;">
        <h4>${props.locationName}</h4>
        <p>${props.address}</p>
      </div>
    `,
    offset: new window.AMap.Pixel(0, -30)
  })

  // 点击标记显示信息窗口
  marker.on('click', function() {
    infoWindow.open(map, marker.getPosition())
  })

  // 调整地图大小
  mapContainer.value.style.height = props.height
  map.on('complete', function() {
    map.resize()
  })
}
</script>

<style scoped>
.map-component {
  padding: 20px;
  background: #ffffff;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  margin: 20px 0;
}

.map-component h3 {
  color: var(--primary-color, #e94840);
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: bold;
  text-align: center;
}

.map-container {
  width: 100%;
  height: 300px;
  border-radius: 8px;
  overflow: hidden;
  margin-bottom: 15px;
}

.map-info {
  text-align: center;
}

.map-title {
  font-size: 16px;
  font-weight: bold;
  color: #333;
  margin-bottom: 5px;
}

.map-address {
  font-size: 14px;
  color: #666;
}

/* 响应式设计 */
@media (max-width: 600px) {
  .map-component {
    padding: 15px;
  }
  
  .map-container {
    height: 250px;
  }
}
</style>