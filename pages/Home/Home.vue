<template>
  <view class="home-container">
    <view class="userinfo" @click="addUser">
      <view class="avatar-left">
        <view class="avatar">
          <view class="avatar_icon"></view>
        </view>
        <view class="name">
          <view class="text_1">微信用户</view>
          <view class="text_2">完善个人信息</view>
        </view>
      </view>

      <view class="add"></view>
    </view>
    <view class="article" @click="toArticle">
      <view class="article_content">
        <view class="article_title">如何吃更科学？如何运动更健康？ </view>
        <view class="article_title">这篇文章有答案～</view>
        <view class="time"
          ><view class="new">NEW</view><text>2023-04-10</text></view
        >
      </view>

      <view class="arrow">
        <view class="arrow_content">
          <view class="left"></view> <view class="right"></view
        ></view>
      </view>
      <!-- <uv-swiper
        height="100%"
        :list="list1"
        @change="(e) => (current1 = e.current)"
        :autoplay="true"
        bgColor="#ffffff"
        radius="30rpx"
      >
        >
        <template v-slot:indicator>
          <view class="indicator">
            <view
              class="indicator__dot"
              v-for="(item, index) in list1"
              :key="index"
              :class="[index === current1 && 'indicator__dot--active']"
            ></view>
          </view>
        </template>
      </uv-swiper> -->
    </view>

    <view class="bottom">
      <view class="ranking">
        <view class="ranking_content">
          <view class="ranking_icon"></view>
          <view class="ranking_title">今日排名</view>
        </view>
        <view class="to_rangking_icon"></view>
      </view>
      <view class="clockin">
        <view class="clockin_day">每日打卡</view>
        <view class="clockin_item">
          <view class="clockin_item_1 itemBorder" @click="toGrowRanking">
            <view class="clockin_content">
              <view
                class="clockin_item_1_text_1 clockin_content_1 clockin_content_buttom"
              >
                生长打卡
              </view>
              <view
                class="clockin_item_1_text_2 clockin_content_2 clockin_content_buttom"
              >
                每日生长记录
              </view>
              <view
                class="clockin_item_1_text_3 clockin_content_3 clockin_content_buttom"
              >
                <view class="check"></view>
              </view>
              <view
                class="clockin_item_1_text_4 clockin_content_4 clockin_content_buttom"
              >
                2000人参与
              </view>
            </view>
          </view>
          <view class="clockin_item_2 itemBorder" @click="toFoodRanking">
            <view class="clockin_content">
              <view
                class="clockin_item_2_text_1 clockin_content_1 clockin_content_buttom"
              >
                膳食打卡
              </view>
              <view
                class="clockin_item_2_text_2 clockin_content_2 clockin_content_buttom"
              >
                每日膳食记录
              </view>
              <view
                class="clockin_item_2_text_3 clockin_content_3 clockin_content_buttom"
              >
                <view class="check"></view>
              </view>
              <view
                class="clockin_item_2_text_4 clockin_content_4 clockin_content_buttom"
              >
                2000人参与
              </view>
            </view>
          </view>
          <view class="clockin_item_3 itemBorder" @click="toExerciseRanking">
            <view class="clockin_content">
              <view
                class="clockin_item_2_text_1 clockin_content_1 clockin_content_buttom"
              >
                运动打卡
              </view>
              <view
                class="clockin_item_2_text_2 clockin_content_2 clockin_content_buttom"
              >
                每日600步
              </view>
              <view
                class="clockin_item_2_text_3 clockin_content_3 clockin_content_buttom"
              >
                <view class="check"></view>
              </view>
              <view
                class="clockin_item_2_text_4 clockin_content_4 clockin_content_buttom"
              >
                2000人参与
              </view>
            </view>
          </view>
        </view>
      </view>

      <view class="food">
        <view class="food_content">
          <view class="food_icon"></view>
          <view class="food_text"> 食物营养成分表 </view>
        </view>
        <view class="to_food"></view>
      </view>
      <view class="health">
        <view class="health_content">
          <view class="health_item_1">
            <view class="health_icon"></view>
            <view class="health_title">健康评估</view>
          </view>
          <view class="health_item_2">提供身体各项指数指标评估 </view>
          <view class="health_item_2">提供指标一场提醒以及改进建议 </view>
        </view>
        <view class="to_health"></view>
      </view>
      <view class="nourishment">
        <view class="nourishment_left">
          <view class="nourishment_left_content">
            <view class="nourishment_left_icon"></view>
            <view class="nourishment_left_text">营养食谱</view></view
          >
        </view>
        <view class="nourishment_right">
          <view class="nourishment_right_item_top">
            <view class="nourishment_top_content">
              <view class="nourishment_top_icon"></view>
              <view class="nourishment_top_text">营养库</view></view
            >
          </view>
          <view class="nourishment_right_item_bottom">
            <view class="nourishment_bottom_content">
              <view class="nourishment_bottom_icon"></view>
              <view class="nourishment_bottom_text">运动指导库</view></view
            >
          </view>
        </view>
      </view>
    </view>
    <button bindtap="onClick" class="button_1"></button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      current1: 0,
      current2: 0,
      list1: ["1", "2", "3"],
    }
  },
  methods: {
    toArticle() {
      uni.reLaunch({
        url: "/pages/Home/ScienceArticle/Article/Article",
      })
    },
    toFoodRanking() {
      uni.reLaunch({
        url: "/pages/Home/Food/Food",
      })
    },
    toGrowRanking() {
      console.log("888")
      uni.reLaunch({
        url: "/pages/Home/Grow/Grow",
      })
    },
    toExerciseRanking() {
      uni.reLaunch({
        url: "/pages/Home/Ranking/Ranking",
      })
    },
    addUser() {
      uni.reLaunch({
        url: "/pages/Home/UserInfo/UserInfo",
      })
    },
  },
}
</script>

<style lang="scss">
page {
  background-color: #efefef;
}
.home-container {
  width: 686rpx;
  height: 1938rpx;
  margin: 0 auto;
  background-color: #efefef;
  position: relative;

  .userinfo {
    width: 100%;
    height: 163rpx;
    display: flex;
    justify-content: space-between;
    .avatar-left {
      display: flex;
      justify-content: center;
      .avatar {
        width: 108rpx;
        height: 108rpx;
        margin-top: 25rpx;
        background-color: #e4e4e4;
        border-radius: 54rpx;
        display: inline-block;
        display: flex;
        justify-content: center;
        align-items: center;

        .avatar_icon {
          width: 38rpx;
          height: 52rpx;
          background: no-repeat center/100%
            url("../../static/icon/02-3profile.png");
        }
      }
      .name {
        height: 108rpx;
        display: inline-block;
        margin-left: 15rpx;
        line-height: 108rpx;
        vertical-align: top;

        .text_1 {
          height: 27rpx;
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 700;
          color: #000000;
          margin-bottom: 5rpx;
        }
        .text_2 {
          font-size: 20rpx;
          font-family: SourceHanSansCN;
          font-weight: 400;
          color: #86858a;
        }
      }
    }
    .add {
      width: 50rpx;
      height: 50rpx;
      margin-top: 50rpx;
      background: no-repeat center/100% url("../../static/icon/white_add.png");
    }
  }
  .article {
    width: 100%;
    height: 454rpx;
    position: relative;
    background-color: #c8c9c9;
    border-radius: 30rpx;
    .article_content {
      top: 39rpx;
      left: 39rpx;
      position: absolute;
      .article_title {
        // margin-top: 39rpx;
        // margin-left: 39rpx;
        font-size: 27rpx;
        font-family: SourceHanSansCN;
        font-weight: 500;
        color: #ffffff;
        line-height: 40rpx;
      }
      .time {
        opacity: 0.4;
        display: flex;
        color: #ffffff;

        .new {
          width: 77rpx;
          height: 33rpx;
          opacity: 0.4;
          border-radius: 10rpx;
          font-size: 22rpx;
          font-weight: 500;
          background-color: #dedfdf;
          line-height: 33rpx;
          text-align: center;
        }
      }
    }
    .arrow {
      position: absolute;
      width: 100%;
      height: 59rpx;
      top: 50%;
      padding-left: 39rpx;

      .arrow_content {
        width: 600rpx;
        display: flex;
        justify-content: space-between;
        .left {
          width: 50rpx;
          height: 51rpx;
          background: no-repeat center/100%
            url("../../static/icon/02-6grey_circle_arrow_left.png");
        }
        .right {
          width: 50rpx;
          height: 51rpx;
          background: no-repeat center/100%
            url("../../static/icon/02-6grey_circle_arrow_right.png");
        }
      }
    }
    @mixin flex($direction: row) {
      /* #ifndef APP-NVUE */
      display: flex;
      /* #endif */
      flex-direction: $direction;
    }
    .indicator {
      @include flex(row);
      justify-content: center;
      &__dot {
        height: 6px;
        width: 6px;
        border-radius: 100px;
        background-color: rgba(255, 255, 255, 0.35);
        margin: 0 5px;
        transition: background-color 0.3s;
        &--active {
          background-color: #ffffff;
        }
      }
    }
    .indicator-num {
      padding: 2px 0;
      background-color: rgba(0, 0, 0, 0.35);
      border-radius: 100px;
      width: 35px;
      @include flex;
      justify-content: center;
      &__text {
        color: #ffffff;
        font-size: 12px;
      }
    }
  }
  .bottom {
    top: 647rpx;
    height: 1069rpx;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;

    .ranking {
      width: 100%;
      height: 108rpx;
      background-color: #fff;
      border-radius: 15rpx;
      font-size: 27rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #000000;
      display: flex;
      justify-content: space-between;

      .ranking_content {
        width: 150rpx;
        display: flex;
        justify-content: space-between;
        margin-top: 35rpx;
        font-weight: 500;
        color: #000000;
        line-height: 31rpx;
        margin-left: 30rpx;
        .ranking_icon {
          width: 32rpx;
          height: 31rpx;
          background: no-repeat center/100%
            url("../../static/icon/02ranking_blue.png");
        }
        .ranking_title {
          font-size: 27rpx;
        }
      }
      .to_rangking_icon {
        width: 51rpx;
        height: 51rpx;
        border-radius: 51rpx;
        border: 2rpx solid #86858a;
        margin-top: 30rpx;
        margin-right: 39rpx;
        background: no-repeat center/100% url("../../static/icon/arrow.png");
      }
    }
    .clockin {
      width: 100%;
      .clockin_day {
        // width: 141rpx;
        height: 34rpx;
        font-size: 36rpx;
        font-family: SourceHanSansCN;
        font-weight: bold;
        color: #000000;
        margin-bottom: 30rpx;
      }
      .clockin_item {
        width: 100%;
        height: 240rpx;
        display: flex;
        color: #fff;
        justify-content: space-between;
        .itemBorder {
          border-radius: 30rpx;
        }
        .clockin_content {
          margin-left: 20rpx;
          margin-top: 26rpx;
          .clockin_content_buttom {
            margin-bottom: 10rpx;
          }
          .clockin_content_1 {
            height: 26rpx;
            font-size: 27rpx;
            font-family: SourceHanSansCN;
            font-weight: 500;
            color: #ffffff;
          }
          .clockin_content_2 {
            height: 19rpx;
            font-size: 20rpx;
            font-family: SourceHanSansCN;
            font-weight: 400;
            color: #ffffff;
            opacity: 0.65;
          }
          .clockin_content_3 {
            width: 65rpx;
            height: 66rpx;
            opacity: 0.47;
          }
          .clockin_content_4 {
            height: 19rpx;
            font-size: 20rpx;
            font-family: SourceHanSansCN;
            font-weight: 400;
            color: #ffffff;
            opacity: 0.65;
          }
        }
        .clockin_item_1 {
          height: 240rpx;
          width: 200rpx;
          background-color: #e2c93b;
          .clockin_content {
            .clockin_item_1_text_3 {
              width: 65rpx;
              height: 66rpx;
              background-color: #fff;
              opacity: 0.6;
              border-radius: 65rpx;
              margin-top: 35rpx;
              .check {
                margin-top: 25rpx;
                margin-left: 8rpx;
                width: 50rpx;
                height: 50rpx;
                background: no-repeat center/100%
                  url("../../static/icon/check.png");
              }
            }
          }
        }
        .clockin_item_2 {
          height: 240rpx;
          width: 216rpx;
          background-color: #90c56e;
          .clockin_item_2_text_3 {
            width: 65rpx;
            height: 66rpx;
            background-color: #fff;
            opacity: 0.6;
            border-radius: 65rpx;
            margin-top: 35rpx;
            .check {
              margin-top: 25rpx;
              margin-left: 8rpx;
              width: 50rpx;
              height: 50rpx;
              background: no-repeat center/100%
                url("../../static/icon/check.png");
            }
          }
        }
        .clockin_item_3 {
          height: 240rpx;
          width: 216rpx;
          background-color: #279da9;
          .clockin_item_2_text_3 {
            width: 65rpx;
            height: 66rpx;
            background-color: #fff;
            opacity: 0.6;
            border-radius: 65rpx;
            margin-top: 35rpx;
            .check {
              margin-top: 25rpx;
              margin-left: 8rpx;
              width: 50rpx;
              height: 50rpx;
              background: no-repeat center/100%
                url("../../static/icon/check.png");
            }
          }
        }
      }
    }
    .food {
      width: 686rpx;
      height: 111rpx;
      background-color: #fff;
      border-radius: 30rpx;
      display: flex;
      justify-content: space-between;
      .food_content {
        width: 250rpx;
        display: flex;
        justify-content: space-between;
        margin-left: 39rpx;
        .food_text {
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #000000;
          margin-top: 24rpx;
          line-height: 51rpx;
        }
        .food_icon {
          width: 51rpx;
          height: 51rpx;
          margin-top: 30rpx;
          // margin-right: 39rpx;
          background: no-repeat center/100% url("../../static/icon/02excel.png");
        }
      }
      .to_food {
        width: 51rpx;
        height: 51rpx;
        border-radius: 51rpx;
        border: 2rpx solid #86858a;
        margin-top: 30rpx;
        margin-right: 39rpx;
        background: no-repeat center/100% url("../../static/icon/arrow.png");
      }
    }
    .health {
      width: 686rpx;
      height: 176rpx;
      background-color: #fff;
      border-radius: 30rpx;
      display: flex;
      justify-content: space-between;
      .health_content {
        .health_item_1 {
          height: 26rpx;
          width: 170rpx;
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #000000;
          margin-top: 24rpx;
          margin-left: 26px;
          display: flex;
          justify-content: space-between;
          .health_icon {
            width: 51rpx;
            height: 51rpx;
            background: no-repeat center/100%
              url("../../static/icon/health_icon.png");
          }
        }
        .health_item_2 {
          height: 19rpx;
          font-size: 20rpx;
          font-family: SourceHanSansCN;
          font-weight: 400;
          color: #86858a;
          margin-top: 20rpx;
          margin-left: 26px;
        }
      }
      .to_health {
        width: 51rpx;
        height: 51rpx;
        border-radius: 51rpx;
        border: 2rpx solid #86858a;
        margin-top: 30rpx;
        margin-right: 39rpx;
        background: no-repeat center/100% url("../../static/icon/arrow.png");
      }
    }
    .nourishment {
      width: 686rpx;
      height: 216rpx;
      display: flex;
      justify-content: space-between;
      .nourishment_left {
        width: 340rpx;
        border-radius: 30rpx;
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        .nourishment_left_content {
          width: 160rpx;
          height: 32rpx;
          display: flex;
          justify-content: space-between;
          .nourishment_left_icon {
            width: 32rpx;
            height: 32rpx;
            background: no-repeat center/100%
              url("../../static/icon/02excel.png");
          }
          .nourishment_left_text {
            line-height: 32rpx;
            font-size: 27rpx;
            font-family: SourceHanSansCN;
            font-weight: 500;
            color: #000000;
          }
        }
      }
      .nourishment_right {
        width: 330rpx;
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-direction: column;
        .nourishment_right_item_top {
          width: 100%;
          height: 96rpx;
          background-color: #fff;
          border-radius: 15rpx;
          display: flex;
          justify-content: center;
          align-items: center;
          .nourishment_top_content {
            width: 130rpx;
            display: flex;
            justify-content: space-between;

            .nourishment_top_icon {
              width: 32rpx;
              height: 32rpx;
              background: no-repeat center/100%
                url("../../static/icon/02database.png");
            }
            .nourishment_top_text {
              line-height: 32rpx;
              font-size: 27rpx;
              font-family: SourceHanSansCN;
              font-weight: 500;
              color: #000000;
            }
          }
        }
        .nourishment_right_item_bottom {
          width: 100%;
          height: 96rpx;
          background-color: #fff;
          border-radius: 15rpx;
          display: flex;
          justify-content: center;
          align-items: center;
          .nourishment_bottom_content {
            width: 190rpx;
            display: flex;
            justify-content: space-between;

            .nourishment_bottom_icon {
              width: 32rpx;
              height: 32rpx;
              background: no-repeat center/100%
                url("../../static/icon/02instruction_blue.png");
            }
            .nourishment_bottom_text {
              line-height: 32rpx;
              font-size: 27rpx;
              font-family: SourceHanSansCN;
              font-weight: 500;
              color: #000000;
            }
          }
        }
      }
    }
  }
}
</style>
