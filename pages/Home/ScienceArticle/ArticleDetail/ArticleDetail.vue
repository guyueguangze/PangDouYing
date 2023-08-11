<template>
  <view class="article_content_container">
    <view class="article_content"> </view>
    <view class="article_bottom">
      <view class="article_time"> 2023-04-10 </view>
      <view class="article_title">
        如何吃更科学？如何运动更健康？ 这篇文章有答案～
      </view>
      <view class="answer_button" @click="toAnswer">
        我已看完文章，去答题
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    toAnswer() {
      uni.reLaunch({
        url: "/pages/Home/ScienceArticle/Answer/Answer",
      })
    },
  },
}
</script>

<style lang="scss">
.article_content_container {
  position: relative;
  .article_content {
    width: 750rpx;
    height: 501rpx;
    background-color: #c8c9c9;
  }
  .article_bottom {
    width: 686rpx;
    margin: 0 auto;
    .article_time {
      height: 15rpx;
      font-size: 20rpx;
      font-family: SourceHanSansCN;
      font-weight: bold;
      color: #8a888e;
      margin-top: 33rpx;
    }
    .article_title {
      width: 540rpx;
      height: 85rpx;
      font-size: 37rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #000000;
      line-height: 49rpx;
      margin-top: 25rpx;
    }
    .answer_button {
      top: 1036rpx;
      left: 32rpx;
      width: 686rpx;
      height: 75rpx;
      color: #fff;
      position: absolute;
      text-align: center;
      line-height: 75rpx;
      background-color: #e2c93b;
      border-radius: 15rpx;
    }
  }
}
</style>
