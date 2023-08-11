<template>
  <view class="page">
    <view class="box_1">
      <image
        src="../../../../static/icon//success_submit.png"
        class="icon_1"
      ></image>
      <text lines="1" class="text_1">提交成功！</text>
      <button @click="backHome" bindtap="onClick" class="button_1">
        <text lines="1" class="text_2">返回首页</text>
      </button>
    </view>
    <!-- <view class="box_2">
      <view class="nav-bar_1">
        <text lines="1" class="text_3">提交成功</text>
      </view>
      <view class="group_1"></view>
    </view> -->
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    backHome() {
      uni.reLaunch({
        url: "/pages/Home/Home",
      })
    },
  },
}
</script>

<style lang="scss">
.page {
  position: relative;
  width: 750rpx;
  height: 1334rpx;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.box_1 {
  width: 750rpx;
  height: 1184rpx;
  background-color: #e2c93b;
  background-size: 100% 100%;
  //   margin-top: 150rpx;
  display: flex;
  flex-direction: column;
}
.icon_1 {
  width: 278rpx;
  height: 278rpx;
  margin: 311rpx 0 0 243rpx;
}
.text_1 {
  width: 118rpx;
  height: 26rpx;
  overflow-wrap: break-word;
  color: rgba(255, 255, 255, 1);
  font-size: 27rpx;
  font-family: SourceHanSansCN-Medium;
  font-weight: 500;
  text-align: left;
  white-space: nowrap;
  line-height: 27rpx;
  margin: 33rpx 0 0 322rpx;
}
.button_1 {
  height: 75rpx;
  background-size: 100% 100%;
  display: flex;
  flex-direction: column;
  width: 685rpx;
  margin: 381rpx 0 80rpx 36rpx;
}
.text_2 {
  width: 108rpx;
  height: 26rpx;
  overflow-wrap: break-word;
  color: rgba(226, 201, 59, 1);
  font-size: 27rpx;
  font-family: SourceHanSansCN-Medium;
  font-weight: 500;
  text-align: left;
  white-space: nowrap;
  line-height: 27rpx;
  margin: 23rpx 0 0 288rpx;
}
.box_2 {
  position: absolute;
  left: 0rpx;
  top: 0rpx;
  width: 750rpx;
  height: 169rpx;
  background: url(https://lanhu.oss-cn-beijing.aliyuncs.com/94c7df56a7529455fcc921635286de1e)
    100% no-repeat;
  background-size: 100% 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-center;
}
.nav-bar_1 {
  height: 89rpx;
  margin-top: 82rpx;
  display: flex;
  flex-direction: column;
  width: 750rpx;
}
.text_3 {
  width: 122rpx;
  height: 30rpx;
  overflow-wrap: break-word;
  color: rgba(0, 0, 0, 1);
  font-size: 31rpx;
  font-family: SourceHanSansCN-Medium;
  font-weight: 500;
  text-align: left;
  white-space: nowrap;
  line-height: 31rpx;
  margin: 30rpx 0 0 319rpx;
}
.group_1 {
  width: 750rpx;
  height: 80rpx;
  margin-bottom: 82rpx;
  display: flex;
  flex-direction: column;
}
</style>
