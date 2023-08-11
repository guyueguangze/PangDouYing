<template>
  <view class="food_container">
    <view class="top">
      <uv-calendars insert />
    </view>
    <view class="middle">
      <view class="time">2023-06-05</view>
      <view class="breakfast">
        <view class="left">
          <view class="breakfast_title">早餐</view>
          <view class="breakfast_suggest">建议500-600千卡</view>
        </view>
        <view class="right">
          <view class="food_icon"></view>
          <view class="right_title">营养分析表</view>
          <view class="to_food_icon"></view>
        </view>
      </view>
      <view>
        <view class="food_list_header">
          <view class="food_list_title"> 菜品名称</view>
          <view class="food_list_title">菜品信息 </view>
          <view class="food_list_title"> 就餐形式</view>
        </view>
        <view class="food_list_data">
          <view> 包子</view>
          <view>馒头（均值）50g 牛奶（草莓味）100g </view>
          <view> 在家</view>
        </view>
      </view>
    </view>
    <view class="bottom">
      <view class="button">
        <uv-button
          type="primary"
          text="营养报告"
          @click="toNutritionReprot"
        ></uv-button>
      </view>
      <view>
        <uv-button
          class="button"
          type="primary"
          text="膳食记录"
          @click="toFoodRecord"
        ></uv-button>
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
    toFoodRecord() {
      uni.reLaunch({
        url: "/pages/Home/Food/FoodRecord/FoodRecord",
      })
    },
    toNutritionReprot() {
      uni.reLaunch({
        url: "/pages/Home/Food/NutritionReport/NutritionReport",
      })
    },
    open() {
      this.$refs.calendars.open()
    },
    confirm(e) {
      console.log(e)
    },
  },
  mounted() {
    this.$refs.calendars.open()
  },
}
</script>

<style lang="scss">
page {
  background-color: #efefef;
}
.food_container {
  width: 750rpx;
  padding: 30rpx;
  background-color: #efefef;
  .top {
    height: 300rpx;
    overflow: hidden;
  }
  .middle {
    width: 686rpx;
    height: 309rpx;
    padding: 15rpx;
    background-color: #fff;
    border-radius: 20rpx;
    margin-top: 70rpx;
    .time {
      font-size: 20rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #989999;
      margin-bottom: 20rpx;
    }
    .breakfast {
      display: flex;
      justify-content: space-between;
      margin-bottom: 50rpx;
      .left {
        display: flex;
        .breakfast_title {
          margin-right: 20rpx;
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #000000;
        }
        .breakfast_suggest {
          font-size: 20rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #90c56e;
        }
      }
      .right {
        width: 127rpx;
        height: 18rpx;
        display: flex;
        justify-content: space-around;
        background-color: #90c56e;
        border-radius: 15rpx;
        padding: 10rpx;
        font-size: 15rpx;
        font-family: SourceHanSansCN;
        font-weight: 500;
        color: #ffffff;
        .food_icon {
          width: 18rpx;
          height: 18rpx;
          background: no-repeat center/100%
            url("../../../static/icon/02-5report.png");
        }
        .right_title {
          line-height: 18rpx;
        }
        .to_food_icon {
          width: 12rpx;
          height: 12rpx;
          background: no-repeat center/100%
            url("../../../static/icon/02-6white_arrow_right_up.png");
        }
      }
    }
    .food_list_header {
      width: 598rpx;
      height: 50rpx;
      display: flex;
      padding: 0 30rpx;
      border-radius: 50rpx;
      background-color: #e9e9eb;
      justify-content: space-between;
      line-height: 50rpx;
      font-size: 20rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #000000;
    }
    .food_list_data {
      width: 598rpx;
      height: 68rpx;
      display: flex;
      padding: 0 30rpx;
      border-radius: 50rpx;
      background-color: #e9e9eb;
      margin-top: 10rpx;
      justify-content: space-between;
      line-height: 68rpx;
      font-size: 15rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #727171;
    }
  }
  .bottom {
    margin-top: 200rpx;
    display: flex;
    justify-content: space-between;
    .button {
      width: 300rpx;
    }
  }
}
</style>
