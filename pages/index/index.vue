<template>
  <view class="content">
    <navbar :isHome="true" />
    <view style="margin-top: 130rpx;">
      <view class="weui-cell" style="background:#fff9eb;">
        <view class="weui-cell__hd">
          <image src="/static/resource/images/ic-myapp.png"
            style="display: block;width: 40rpx;height: 40rpx;margin-right: 14rpx;"></image>
        </view>
        <view class="weui-cell__bd">
          <text style="color: #be9719;font-size: 13rpx;">点击右下角“添加到我的小程序”，方便下次找到</text>
        </view>
        <view class="weui-cell__ft">
          <image src="/static/resource/images/modal_closer.png" style="display: block;width: 15px;height: 15px;">
          </image>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup>
import { ref } from 'vue'
const data = ref('动态数组')
//跳转搜索页
const navigaterTo = () => {
  uni.navigateTo({
    url: '/pages/search/index'
  })
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
