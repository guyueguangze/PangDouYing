<template>
  <view class="answer-container">
    <view class="topic">
      <uv-line-progress
        :percentage="50"
        activeColor="#E2C93B"
        :showText="false"
      ></uv-line-progress>
      <view class="question">Q1: 你认为控制饮食重要吗？</view>
      <!-- <view class="select"
        ><uni-section title="单选" type="list" mode="list">
          <view class="uni-px-5 uni-pb-5">
            <uni-data-checkbox
              v-model="radio1"
              :localdata="question"
            ></uni-data-checkbox>
          </view> </uni-section
      ></view> -->
      <radio-group>
        <view class="option">
          <radio
            :class="item.id == 1 ? 'isYellow' : ''"
            v-for="item in radioList"
            :key="item.id"
            :value="item.checked"
          >
            {{ item.label }}
          </radio>
        </view>
      </radio-group>
    </view>
    <view class="box_2 flex-col" @click="done">
      <view class="image-wrapper_1 flex-col">
        <image
          class="label_1"
          referrerpolicy="no-referrer"
          src="../../../../static/icon/02-2right_arrow.png"
        />
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      // radio1: "",
      radioList: [
        {
          id: 1,
          label: "选项1",
          checked: false,
        },
        {
          id: 2,
          label: "选项2",
          checked: false,
        },
        {
          id: 3,
          label: "选项3",
          checked: false,
        },
        {
          id: 4,
          label: "选项4",
          checked: false,
        },
      ],
    }
  },
  methods: {
    done() {
      console.log("55")
      uni.reLaunch({
        url: "/pages/Home/ScienceArticle/sbumitSuccess/sbumitSuccess",
      })
    },
  },
}
</script>

<style lang="scss">
.answer-container {
  width: 750rpx;
  height: 1000rpx;
  position: relative;
  .topic {
    width: 686rpx;
    height: 567rpx;
    top: 47rpx;
    left: 35rpx;
    position: absolute;
    margin: 0 auto;
    // margin-top: 67rpx;
  }
  .question {
    margin-top: 30rpx;
    font-weight: 500;
  }
  .option {
    display: block;
    margin-top: 50rpx;
    .isYellow {
      background-color: #e2c93b;
    }
    uni-radio {
      width: 600rpx;
      height: 90rpx;
      background-color: #fff;
      border-radius: 15rpx;
      margin-bottom: 30rpx;
      padding-left: 50rpx;
      ::v-deep .uni-radio-wrapper {
        line-height: 90rpx !important;

        .uni-radio-input {
          background-color: #e4e4e4;
        }
        ::v-deep.uni-radio-input-checked::after {
          background-color: green !important;
        }
        ::v-deep .uni-radio-input-checked:before {
          color: #e2c93b;
          //  {
          //   color: #e2c93b;
          // }
        }
      }
    }
  }
  .image-wrapper_1 {
    position: absolute;
    top: 980rpx;
    left: 600rpx;
    height: 106rpx;
    background-size: 100% 100%;
    width: 105rpx;
  }

  .label_1 {
    width: 105rpx;
    height: 106rpx;
    margin: 37rpx 0 0 37rpx;
  }
}
</style>
