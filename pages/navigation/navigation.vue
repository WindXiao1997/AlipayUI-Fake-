
<template>
  <view class="container">
    <!-- 顶部搜索栏 -->
    <view class="search-container">
      <view class="search-bar">
        <image class="search-icon" src="/static/icon/search.png"></image>
        <text class="search-placeholder">热门番剧:纯白交响曲</text>
        <image class="huatong-icon" src="/static/icon/huatong.png"></image>
      </view>
      <view class="right-icons">
        <image class="right-icon" src="/static/icon/my.png"></image>
        <image class="right-icon" src="/static/icon/jia.png"></image>
      </view>
    </view>

    <!-- 顶部功能区域 -->
    <view class="top-functions">
      <view class="function-item" @click="scanQR">
        <image class="icon" src="/static/icon/saoyisao.png"></image>
        <text class="label">扫一扫</text>
      </view>
      <view class="function-item" @click="search">
        <image class="icon" src="/static/icon/money.png"></image>
        <text class="label">收款</text>
      </view>
      <view class="function-item" @click="pay">
        <image class="icon" src="/static/icon/money.png"></image>
        <text class="label">付款</text>
      </view>
      <view class="function-item" @click="card">
        <image class="icon" src="/static/icon/kabao.png"></image>
        <text class="label">卡包</text>
      </view>
    </view>

    <!-- 九宫格导航区域 -->
    <view class="grid-container">
      <view 
        class="grid-item" 
        v-for="(item, index) in gridItems" 
        :key="index"
        @click="navigateTo(item.path)"
      >
        <image class="grid-icon" :src="item.icon"></image>
        <text class="grid-label">{{ item.label }}</text>
      </view>
    </view>
  </view>
</template>

<script setup>
import { ref } from 'vue'

const gridItems = ref([
  { icon: '/static/icon/koubei.png', label: '口碑', path: '/pages/koubei' },
  { icon: '/static/icon/CivicCenter.png', label: '市民中心', path: '/pages/civic' },
  { icon: '/static/icon/zhuanzhang2.png', label: '转账', path: '/pages/transfer' },
  { icon: '/static/icon/creditcard.png', label: '还款', path: '/pages/repayment' },
  { icon: '/static/icon/elma.png', label: '饿了么', path: '/pages/elma' },
  { icon: '/static/icon/farm.png', label: '芭芭农场', path: '/pages/farm' },
  { icon: '/static/icon/yuebao.png', label: '余额宝', path: '/pages/yuebao' },
  { icon: '/static/icon/huabei.png', label: '花呗', path: '/pages/huabei' },
  { icon: '/static/icon/didi.png', label: '滴滴', path: '/pages/didi' },
  { icon: '/static/icon/sesame.png', label: '芝麻信用', path: '/pages/sesame' },
  { icon: '/static/icon/kkb.png', label: '看看哔', path: '/pages/bilibili' },
  { icon: '/static/icon/jiebei.png', label: '借呗', path: '/pages/jiebei' },
  { icon: '/static/icon/health.png', label: '医疗健康', path: '/pages/health' },
  { icon: '/static/icon/mayizhuanyuan.png', label: '蚂蚁庄园', path: '/pages/manor' },
  { icon: '/static/icon/all.png', label: '更多', path: '/pages/all' }
])
//Project Designed by Github@Windxiao1997
const scanQR = () => {
  uni.showToast({ title: '扫一扫功能', icon: 'none' })
}

const search = () => {
  uni.showToast({ title: '收钱功能', icon: 'none' })
}

const pay = () => {
  uni.showToast({ title: '付款功能', icon: 'none' })
}

const card = () => {
  uni.showToast({ title: '卡包功能', icon: 'none' })
}

const navigateTo = (path) => {
  uni.navigateTo({ url: path })
}
</script>

<style scoped>
.container {
  padding: 0;
}

.search-container {
  display: flex;
  align-items: center;
  background-color: #1E90FF;
  padding: 20rpx;
  border-top-left-radius: 20rpx;
  border-top-right-radius: 20rpx;
}

.search-bar {
  flex: 1;
  display: flex;
  align-items: center;
  background-color: #f5f5f5;
  border-radius: 40rpx;
  padding: 10rpx 20rpx;
}

.search-icon {
  width: 40rpx;
  height: 40rpx;
  margin-right: 10rpx;
}

.search-placeholder {
  flex: 1;
  font-size: 28rpx;
  color: #999;
}

.huatong-icon {
  width: 40rpx;
  height: 40rpx;
  margin-left: 10rpx;
}

.right-icons {
  display: flex;
  margin-left: 20rpx;
}

.right-icon {
  width: 50rpx;
  height: 50rpx;
  margin-left: 20rpx;
}

.top-functions {
  display: flex;
  justify-content: space-around;
  padding: 30rpx 0;
  background-color: #1E90FF;
  border-bottom-left-radius: 20rpx;
  border-bottom-right-radius: 20rpx;
  margin-bottom: 20rpx;
}

.function-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.icon {
  width: 80rpx;
  height: 80rpx;
  margin-bottom: 10rpx;
}

.label {
	color: white;
	font-weight: bold;
}


.grid-container {
  display: flex;
  flex-wrap: wrap;
  padding: 10rpx 0;
}

.grid-item {
  width: 20%; /* 确保5列 */
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 20rpx; /* 行间距 */
  box-sizing: border-box;
  padding: 10rpx;
}

.grid-icon {
  width: 50rpx; /* 更小的图标 */
  height: 50rpx;
  margin-bottom: 5rpx;
}

.grid-label {
  font-size: 20rpx;
  color: #333;
  text-align: center;
  line-height: 1.2;
}

</style>
