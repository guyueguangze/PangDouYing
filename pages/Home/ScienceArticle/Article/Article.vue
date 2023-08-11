<template>
  <view class="article-container">
    <view class="article-list" @click="toArticleDetail">
      <view class="time">2023-04-10</view>
      <view class="title">
        <view>如何吃更科学？如何运动更健康？</view>
        <view> 这篇文章有答案～</view>
      </view>

      <view class="rigthArrows"> </view>
    </view>
    <view class="article-list" @click="toArticleDetail">
      <view class="time">2023-04-10</view>
      <view class="title">
        <view>如何吃更科学？如何运动更健康？</view>
        <view> 这篇文章有答案～</view>
      </view>

      <view class="rigthArrows"> </view>
    </view>
    <view class="article-list" @click="toArticleDetail">
      <view class="time">2023-04-10</view>
      <view class="title">
        <view>如何吃更科学？如何运动更健康？</view>
        <view> 这篇文章有答案～</view>
      </view>

      <view class="rigthArrows"> </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    toArticleDetail() {
      uni.reLaunch({
        url: "/pages/Home/ScienceArticle/ArticleDetail/ArticleDetail",
      })
    },
  },
}
</script>

<style lang="scss">
.article-container {
  width: 100%;

  .article-list {
    width: 686rpx;
    height: 454rpx;
    position: relative;
    margin: 20rpx auto;
    background-color: #c8c9c9;
    border-radius: 30rpx;
    .time {
      position: absolute;
      top: 31rpx;
      left: 37rpx;
      color: #fff;
      font-size: 24rpx;
    }
    .title {
      position: absolute;
      top: 346rpx;
      left: 32rpx;
      color: #fff;
      font-size: 27rpx;
    }
    .rigthArrows {
      position: absolute;
      width: 51rpx;
      height: 51rpx;
      top: 357rpx;
      left: 599rpx;
      image {
        width: 100%;
        height: 100%;
      }
      background: no-repeat center/100%
        url("../../../../static/rightArrows.png");
    }
  }
}
</style>
