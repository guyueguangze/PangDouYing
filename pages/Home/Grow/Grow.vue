<template>
  <view class="grow_container">
    <view class="body_data">
      <uv-form labelPosition="left">
        <view class="body_data_1">
          <uv-form-item label="身高" borderBottom>
            <uv-input placeholder="请输入当前身高（cm）" border="none">
            </uv-input>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="体重" borderBottom>
            <uv-input placeholder="请输入当前体重（kg）" border="none">
            </uv-input>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="腰围" borderBottom>
            <uv-input placeholder="请输入当前腰围（cm）" border="none">
            </uv-input>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="头围" borderBottom>
            <uv-input placeholder="请输入当前头围（cm）" border="none">
            </uv-input>
          </uv-form-item>
        </view>
      </uv-form>
    </view>
    <view class="heart">
      <view class="heart_data">
        <view class="title">心率</view>
        <view class="num">76</view>
      </view>
      <view class="time">15.18</view>
    </view>
    <view class="blood_pressure">
      <view class="blood_pressure_data">
        <view class="title">血压</view>
        <view class="num">102<text>高压</text></view>
        <view class="num">79<text>低压</text></view>
      </view>
      <view class="time">15.18</view>
    </view>
    <view class="heart">
      <view class="heart_data">
        <view class="title">血氧饱和度</view>
        <view class="num">96%</view>
      </view>
      <view class="time">15.18</view>
    </view>
    <view class="body_data">
      <uv-form labelPosition="left" labelWidth="130rpx">
        <view class="body_data_1">
          <uv-form-item label="小便颜色" borderBottom>
            <uv-input placeholder="请选择小便颜色" border="none"> </uv-input>
            <template v-slot:right>
              <view class="arrow-right"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="大便形状" borderBottom>
            <uv-input placeholder="请选择大便形状" border="none"> </uv-input>
            <template v-slot:right>
              <view class="arrow-right"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="大便颜色" borderBottom>
            <uv-input placeholder="请选择大便颜色" border="none"> </uv-input>
            <template v-slot:right>
              <view class="arrow-right"></view>
            </template>
          </uv-form-item>
        </view>
        <view class="body_data_1">
          <uv-form-item label="大便重量" borderBottom>
            <uv-input placeholder="请选择大便重量" border="none"> </uv-input>
            <template v-slot:right>
              <view class="arrow-right"></view>
            </template>
          </uv-form-item>
        </view>
      </uv-form>
    </view>
    <view class="report">
      <view class="report_title">
        <view class="report_icon"> </view>

        <view class="title"> 生成健康评估报告</view>
      </view>
      <view class="to_report"> </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>

<style lang="scss">
::v-deep .arrow-right {
  width: 48rpx;
  height: 49rpx;
  background: no-repeat center/100%
    url("../../../static/icon/02-3yellow_plus.png");
}
page {
  background-color: #efefef;
}
.grow_container {
  height: 1900rpx;
  padding: 30rpx;

  .body_data {
    background-color: #fff;
    border-radius: 30rpx;
    margin-bottom: 19rpx;
    .body_data_1 {
      padding-left: 30rpx;
      padding-right: 30rpx;
    }
  }
  .heart {
    width: 636rpx;
    height: 164rpx;
    padding: 30rpx;
    display: flex;
    justify-content: space-between;
    margin-top: 19rpx;
    margin-bottom: 19rpx;
    background-color: #fff;
    border-radius: 30rpx;
    .heart_data {
      .title {
        font-size: 23rpx;
        font-family: SourceHanSansCN;
        font-weight: 700;
        color: #87868a;
        margin-bottom: 50rpx;
      }
      .num {
        height: 77rpx;
        font-size: 69rpx;
        font-family: SourceHanSansCN;
        font-weight: bold;
        color: #e2c93b;
      }
    }

    .time {
      font-size: 23rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #87868a;
    }
  }
  .blood_pressure {
    width: 636rpx;
    height: 277rpx;
    padding: 30rpx;
    display: flex;
    justify-content: space-between;
    margin-top: 19rpx;
    background-color: #fff;
    border-radius: 30rpx;
    .blood_pressure_data {
      .title {
        font-size: 23rpx;
        font-family: SourceHanSansCN;
        font-weight: 700;
        color: #87868a;
        margin-bottom: 50rpx;
      }
      .num {
        height: 77rpx;
        font-size: 69rpx;
        font-family: SourceHanSansCN;
        font-weight: bold;
        color: #e2c93b;
        text {
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #87868a;
        }
      }
    }

    .time {
      font-size: 23rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #87868a;
    }
  }
  .report {
    width: 626rpx;
    height: 46rpx;
    background-color: #e2c93b;
    border-radius: 15rpx;
    padding: 15rpx 30rpx;
    margin-top: 67rpx;
    display: flex;
    justify-content: space-between;
    .report_title {
      margin-top: 5rpx;
      display: flex;
      justify-content: space-between;
      .report_icon {
        width: 32rpx;
        height: 32rpx;
        margin-right: 20rpx;
        background: no-repeat center/100%
          url("../../../static/icon/02-5report.png");
      }
      .title {
        font-size: 27rpx;
        font-family: SourceHanSansCN;
        font-weight: 500;
        color: #ffffff;
        line-height: 32rpx;
      }
    }
    .to_report {
      width: 48rpx;
      height: 48rpx;
      background: no-repeat center/100%
        url("../../../static/icon/02-5arrow_right_up.png");
    }
  }
}
</style>
