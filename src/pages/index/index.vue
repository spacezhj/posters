<template>
  <view class="conference-detail-page">
    <!-- 会议信息 -->
    <view class="conference-info">
      <image src="@/static/image/bg.jpg" mode="aspectFill" class="banner"></image>

      <view class="title-box">
        <text class="title">青岛鼻科论坛、青岛睡眠论坛、青岛耳鼻咽喉头颈外科学术会议</text>
        <view class="date">时间：2024-11-23至2024-11-24</view>
      </view>
    </view>

    <!-- 直播间入口 -->
    <view class="live-room">
      <image src="@/static/image/btn.png" class="live-btn" />
    </view>

    <!-- 直播封面图 -->
    <view class="live-cover" @click="navigateToLiveRoom">
      <image src="@/static/image/video.jpg" class="cover-image"></image>
      <image src="@/static/image/play.png" class="play-btn"/>
    </view>

<!--    弹窗提示 showToast-->
    <view class="total-box" v-if="showToast">
        直播间已结束
    </view>

  </view>
</template>

<script setup>
import {ref} from 'vue';

const showToast = ref(false);
// 跳转到直播间
const navigateToLiveRoom = () => {
 showToast.value = !showToast.value
  setTimeout(()=>{
    showToast.value = !showToast.value
  },1500)
};
</script>

<style lang="scss" scoped>
.conference-detail-page {

  .conference-info {


    .banner {
      width: 100%;
      height: 345rpx;
      margin-bottom: 32rpx;
    }

    .title-box {
      padding: 0 28rpx;
    }

    .title {
      font-size: 33rpx;
      color: #333333;;
      font-weight: bold;
      margin-bottom: 30rpx;
    }

    .date {
      font-size: 25rpx;
      color: #999999;
    }
  }

  .live-room {
    margin-top: 100rpx;
    text-align: center;

    .live-btn {
      margin: 0 auto;
      width: 202rpx;
      height: 90rpx;
    }
  }

  .live-cover {
    position: relative;
    margin-top: 40rpx;
    padding: 0 67rpx;

    .cover-image {
      width: 100%;
      height: 335rpx;
      border-radius: 13rpx;
    }

    .play-btn {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 80rpx;
      height: 80rpx;
      transform: translate(-50%, -50%);
      //background-color: rgba(0, 0, 0, 0.5);
      border-radius: 50%;
      //padding: 20rpx;
      //box-shadow: 0 2rpx 10rpx rgba(0, 0, 0, 0.1);
    }
  }

  .total-box{
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 10rpx 15rpx;
    width: fit-content;
    border-radius: 20rpx;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
    text-align: center;
    font-size: 50rpx;
  }
}
</style>
