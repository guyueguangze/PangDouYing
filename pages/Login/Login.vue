<template>
  <view class="container">
    <view class="login-container">
      <image src="../../static/loginImage.png" class="loginImage"></image>

      <!-- 提示登录的图标 -->
      <view class="phone">
        <input
          class="input"
          v-model="phone"
          focus
          placeholder="请输入您的手机号"
          @input="input"
        />
      </view>
      <view class="loginButton" @click="handleLogin">
        登录
        <!-- <button class="button" type="primary" @click="handleLogin">登录</button> -->
      </view>
    </view>
  </view>
</template>
<script>
export default {
  data() {
    return {
      phone: "",
    }
  },
  methods: {
    input() {
      console.log("5555")
    },
    handleLogin() {
      uni.reLaunch({
        url: "/pages/Home/Home",
      })
    },
  },
}
</script>
<style>
page {
  background-color: #b0b0b1;
}
.login-container {
  width: 750rpx;
  height: 1165rpx;
  background-color: #b0b0b1;
  position: relative;
}
.loginImage {
  width: 431rpx;
  height: 150rpx;
  position: absolute;
  top: 217rpx;
  left: 150rpx;
}
.phone {
  width: 686rpx;
  height: 76rpx;
  top: 834rpx;
  left: 34rpx;
  position: absolute;
  border-radius: 30rpx;
}
input {
  width: 686rpx;
  height: 76rpx;
  border-radius: 15rpx;
  background-color: #9e9f9f;
}
.input-placeholder {
  width: 200rpx;
  height: 50rpx;
  font-size: 20rpx;
  color: #efefef;
  margin-left: 30rpx;
}
.uni-input-input {
  width: 500rpx;
  height: 76rpx;
  border-radius: 30rpx;
}
.loginButton {
  width: 685rpx;
  height: 75rpx;
  top: 942rpx;
  left: 35rpx;
  position: absolute;
  border-radius: 15rpx;
  background-color: #fff;
  text-align: center;
  line-height: 75rpx;
  font-size: 27rpx;
  color: #9e9f9f;
}
.button {
  width: 685rpx;
  height: 75rpx;
}
</style>
