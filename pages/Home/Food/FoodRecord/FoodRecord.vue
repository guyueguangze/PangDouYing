<template>
  <view class="food_record_conttainer">
    <view class="record_form">
      <uv-form labelPosition="left" labelWidth="220rpx">
        <view class="body_data_1">
          <uv-form-item label="请选择餐别" borderBottom>
            <uv-input border="none"> </uv-input>
            <template v-slot:right>
              <view class="add_green"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="请选择烹饪方式" borderBottom>
            <uv-input border="none"> </uv-input>
            <template v-slot:right>
              <view class="add_green"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="请选择就餐地点" borderBottom>
            <uv-input border="none"> </uv-input>
            <template v-slot:right>
              <view class="add_green"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="请输入菜品名称">
            <uv-input border="none"> </uv-input>
            <template v-slot:right>
              <view class="cuisine" @click="toCuisine">菜品库</view>
            </template>
          </uv-form-item>
        </view>
      </uv-form>
    </view>

    <view class="photograph">
      <view class="photograph_content">
        <view class="photograph_icon"></view>
        <view class="photograph_text">拍照上传您的食物</view>
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
    toCuisine() {
      uni.reLaunch({
        url: "/pages/Home/Food/Cuisine/Cuisine",
      })
    },
  },
}
</script>

<style lang="scss">
::v-deep .add_green {
  width: 48rpx;
  height: 49rpx;
  background: no-repeat center/100%
    url("../../../../static//icon/02-6-1-1-2green_plus.png");
}
.food_record_conttainer {
  padding: 30rpx;
  .record_form {
    width: 646rpx;
    height: 400rpx;
    background-color: #fff;
    border-radius: 30rpx;
    padding: 20rpx;
    .cuisine {
      width: 109rpx;
      height: 50rpx;
      background-color: #90c56e;
      border-radius: 10rpx;
      text-align: center;
      line-height: 50rpx;
      font-size: 20rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #ffffff;
    }
  }
  .photograph {
    width: 688rpx;
    height: 89rpx;
    background-color: #90c56e;
    border-radius: 89rpx;
    margin-top: 55rpx;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
    .photograph_content {
      margin-top: 30rpx;
      display: flex;
      justify-content: space-between;
      .photograph_icon {
        width: 32rpx;
        height: 31rpx;
        background: no-repeat center/100%
          url("../../../../static//icon/02-6-1white_capture.png");
      }
      .photograph_text {
        line-height: 30rpx;
        margin-left: 15rpx;
        font-size: 27rpx;
        font-family: SourceHanSansCN;
        font-weight: 500;
        color: #ffffff;
      }
    }
  }
}
</style>
