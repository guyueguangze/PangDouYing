<template>
  <view class="add_page">
    <view class="add_page_container">
      <view class="user-avatar">
        <view class="avatar-left">
          <view class="avatar">
            <view class="avatar_icon"></view>
          </view>
          <view class="name">
            <view class="text_1">添加头像</view>
          </view>
        </view>

        <view class="add"></view>
      </view>
      <view class="userInfor">
        <uv-form labelPosition="left" :model="model1" :rules="rules" ref="form">
          <view class="userInfor_1">
            <uv-form-item
              label="姓名"
              prop="userInfo.name"
              borderBottom
              ref="item1"
              placeholder="请输入真实姓名"
            >
              <uv-input v-model="model1.userInfo.name" border="none">
              </uv-input>
            </uv-form-item>
            <uv-form-item
              label="性别"
              prop="userInfo.sex"
              borderBottom
              @click="showSexSelect"
              ref="item1"
            >
              <uv-input
                v-model="model1.userInfo.sex"
                disabled
                disabledColor="#ffffff"
                placeholder="请选择性别"
                border="none"
              >
              </uv-input>
              <template v-slot:right>
                <view class="arrow-right"></view>
              </template>
            </uv-form-item>
            <uv-form-item
              @click="openCalendars"
              label="出生日期"
              prop="userInfo.name"
              borderBottom
              ref="item1"
              placeholder="请选择出生日期"
            >
              <uv-input v-model="model1.userInfo.name" border="none">
              </uv-input>
              <template v-slot:right>
                <view class="arrow-right"></view>
              </template>
            </uv-form-item>
            <uv-form-item
              label="成员关系"
              placeholder="请选择与成员关系"
              prop="userInfo.name"
              ref="item1"
            >
              <uv-input v-model="model1.userInfo.name" border="none">
              </uv-input>
              <template v-slot:right>
                <view class="arrow-right"></view>
              </template>
            </uv-form-item>
          </view>
          <view class="userInfor_2">
            <view class="save">
              <view class="save_icon"></view>
            </view>

            <uv-form-item
              label="所在城市"
              prop="userInfo.sex"
              borderBottom
              @click="showSexSelect"
              ref="item1"
            >
              <uv-input
                v-model="model1.userInfo.sex"
                disabled
                disabledColor="#ffffff"
                placeholder="请选择所在城市"
                border="none"
              >
              </uv-input>
              <template v-slot:right>
                <view class="arrow-right"></view>
              </template>
            </uv-form-item>
            <uv-form-item
              label="所在学校"
              prop="userInfo.name"
              borderBottom
              ref="item1"
            >
              <uv-input
                v-model="model1.userInfo.name"
                border="none"
                placeholder="请输入所在学校"
              >
              </uv-input>
            </uv-form-item>
            <uv-form-item
              label="班级"
              prop="userInfo.name"
              borderBottom
              ref="item1"
            >
              <uv-input
                v-model="model1.userInfo.name"
                border="none"
                placeholder="请输入所在班级"
              >
              </uv-input>
            </uv-form-item>
            <uv-form-item
              label="身份证"
              prop="userInfo.name"
              borderBottom
              ref="item1"
            >
              <uv-input
                v-model="model1.userInfo.name"
                border="none"
                placeholder="请输入身份证号"
              >
              </uv-input>
            </uv-form-item>
            <uv-form-item label="手机号" prop="userInfo.name" ref="item1">
              <uv-input
                v-model="model1.userInfo.name"
                border="none"
                placeholder="请输入手机号"
              >
              </uv-input>
            </uv-form-item>
          </view>
          <view class="userInfor_3">
            <view class="userInfor_3_border">
              <uv-form-item
                label="血型"
                placeholder="请选择血型"
                prop="userInfo.name"
                ref="item1"
              >
                <uv-input v-model="model1.userInfo.name" border="none">
                </uv-input>
                <template v-slot:right>
                  <view class="arrow-white"></view>
                </template>
              </uv-form-item>
            </view>
            <view class="userInfor_3_border">
              <uv-form-item label="当前身高" prop="userInfo.name" ref="item1">
                <uv-input
                  v-model="model1.userInfo.name"
                  border="none"
                  placeholder="请输入当前身高（cm）"
                >
                </uv-input>
              </uv-form-item>
            </view>
            <view class="userInfor_3_border">
              <uv-form-item label="当前体重" prop="userInfo.name" ref="item1">
                <uv-input
                  v-model="model1.userInfo.name"
                  border="none"
                  placeholder="请输入当前体重（kg）"
                >
                </uv-input>
              </uv-form-item>
            </view>
          </view>
          <view class="userInfo_4">
            <view class="title_1">个人健康史</view>
            <view class="title_2">慢性病史或其他疾病史</view>
            <view class="title_3">您是否患有重症疾病或其他慢性疾病？</view>
            <view class="openClose yellowbackground">
              <view class="close_father" @click="handleIsIllness">
                <view
                  class="circle"
                  :class="isillness ? '' : 'circleBorder'"
                ></view>
                <view class="open" v-show="isillness ? true : false"> </view
              ></view>
              <view class="close_father" @click="handleNoIllness">
                <view class="close" v-show="isillness ? false : true">
                  <view class="fork"></view>
                </view>
              </view>
            </view>
            <view class="title_2">家族史</view>
            <view class="title_3"
              >您是否有家人患有重症疾病或其他慢性疾病？</view
            >
            <view class="openClose yellowbackground">
              <view class="close_father" @click="handleIsIllness">
                <view
                  class="circle"
                  :class="isillness ? '' : 'circleBorder'"
                ></view>
                <view class="open" v-show="isillness ? true : false"> </view
              ></view>
              <view class="close_father" @click="handleNoIllness">
                <view class="close" v-show="isillness ? false : true">
                  <view class="fork"></view>
                </view>
              </view>
            </view>
            <view class="title_2">食物过敏史</view>
            <view class="title_3">您是否有食物过敏史？</view>
            <view class="openClose">
              <view class="close_father" @click="handleIsIllness">
                <view
                  class="circle"
                  :class="isillness ? '' : 'circleBorder'"
                ></view>
                <view class="open" v-show="isillness ? true : false"> </view
              ></view>
              <view class="close_father" @click="handleNoIllness">
                <view class="close" v-show="isillness ? false : true">
                  <view class="fork"></view>
                </view>
              </view>
            </view>
            <view class="title_2">药物过敏史</view>
            <view class="title_3">您是否有药物过敏史？</view>
            <view class="openClose">
              <view class="close_father" @click="handleIsIllness">
                <view
                  class="circle"
                  :class="isillness ? '' : 'circleBorder'"
                ></view>
                <view class="open" v-show="isillness ? true : false"> </view
              ></view>
              <view class="close_father" @click="handleNoIllness">
                <view class="close" v-show="isillness ? false : true">
                  <view class="fork"></view>
                </view>
              </view>
            </view>
            <view class="title_2">接触过敏史</view>
            <view class="title_3">您是否有接触过敏史？</view>
            <view class="openClose">
              <view class="close_father" @click="handleIsIllness">
                <view
                  class="circle"
                  :class="isillness ? '' : 'circleBorder'"
                ></view>
                <view class="open" v-show="isillness ? true : false"> </view
              ></view>
              <view class="close_father" @click="handleNoIllness">
                <view class="close" v-show="isillness ? false : true">
                  <view class="fork"></view>
                </view>
              </view>
            </view>
            <view class="title_2">请填写您的过敏原</view>
            <uv-input placeholder="" border="surround"></uv-input>
          </view>
          <view class="footer">
            <view class="setDefault">
              <view>设为默认</view>
              <uv-switch activeColor="#e2c93b"></uv-switch>
            </view>
            <view class="setButton"
              ><uv-button
                class="cancleutton"
                type="primary"
                text="取消"
                color="#E4E4E4"
              ></uv-button
              ><uv-button
                class="confirmbutton"
                type="primary"
                text="确定添加"
                color="#e2c93b"
              ></uv-button
            ></view>
          </view>
          <view> </view>
        </uv-form>
      </view>
    </view>
    <uv-calendars ref="calendars" @confirm="confirm" />
    <uv-action-sheet
      ref="sexSelect"
      :actions="actions"
      title="请选择性别"
      description="如果选择保密会报错"
      @select="sexSelect"
    >
    </uv-action-sheet>
  </view>
</template>

<script>
export default {
  data() {
    return {
      model1: { userInfo: {} },
      rules: {},
      value: false,
      actions: ["男", "女"],
      isillness: false,
    }
  },
  methods: {
    openCalendars() {
      this.$refs.calendars.open()
      console.log("22")
    },
    confirm() {
      this.$refs.calendars.open()
      console.log("22")
    },
    // 性别选择
    showSexSelect() {
      this.$refs.sexSelect.open()
      this.hideKeyboard()
    },
    handleIsIllness() {
      this.isillness = true
      console.log(1)
    },
    handleNoIllness() {
      this.isillness = false
      console.log("2")
    },
  },
}
</script>
<style lang="scss">
.add_page {
  width: 750rpx;
  height: 3330rpx;
  background-color: #efefef;
  .add_page_container {
    width: 686rpx;
    margin: 0 auto;
    .user-avatar {
      width: 100%;
      height: 163rpx;
      display: flex;
      justify-content: space-between;
      margin-bottom: 20rpx;
      .avatar-left {
        width: 300rpx;
        display: flex;
        justify-content: space-between;
        margin-top: 35rpx;
        .avatar {
          width: 115rpx;
          height: 115rpx;
          background-color: #e2c93b;
          border-radius: 115rpx;
          display: inline-block;
          display: flex;
          justify-content: center;
          align-items: center;
          .avatar_icon {
            width: 38rpx;
            height: 53rpx;
            background: no-repeat center/100%
              url("../../../static/icon/02-3profile.png");
          }
        }
        .name {
          height: 108rpx;
          display: inline-block;
          // margin-left: 111rpx;
          line-height: 108rpx;
          // vertical-align: top;
          .text_1 {
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
        // text-align: center;
        // border-radius: 25rpx;
        // border: 1rpx solid #e2c93b;
        // background-color: #e2c93b;
        color: #fff;
        background: no-repeat center/100%
          url("../../../static/icon/02-3yellow_plus.png");
      }
    }
    .userInfor {
      .userInfor_1 {
        padding: 30rpx;
        background-color: #fff;
        border-radius: 30rpx;
      }
      .userInfor_2 {
        position: relative;
        padding: 30rpx;
        background-color: #fff;
        border-radius: 30rpx;
        margin-top: 30rpx;
        .save {
          width: 88rpx;
          height: 89rpx;
          top: 492rpx;
          left: 599rpx;
          position: absolute;
          background-color: #fff;
          border-radius: 90rpx;
          border: 2rpx solid #efefef;
          border-width: 4rpx;
          display: flex;
          justify-content: center;
          align-items: center;
          .save_icon {
            width: 40rpx;
            height: 39rpx;

            background: no-repeat center/100%
              url("../../../static/icon/02-3save.png");
          }
        }
      }
      .userInfor_3 {
        position: relative;
        margin-top: 30rpx;
        .userInfor_3_border {
          padding: 0 30rpx;
          background-color: #e1e1e1;
          border: 1rpx solid #e1e1e1;
          border-radius: 20rpx;
          margin-bottom: 30rpx;
        }
      }
      .userInfo_4 {
        .title_1 {
          height: 35rpx;
          font-size: 36rpx;
          font-family: SourceHanSansCN;
          font-weight: bold;
          color: #000000;
          margin-bottom: 39rpx;
        }
        .title_2 {
          height: 27rpx;
          font-size: 27rpx;
          font-family: SourceHanSansCN;
          font-weight: 500;
          color: #000000;
          margin-bottom: 18rpx;
        }
        .title_3 {
          height: 19rpx;
          font-size: 20rpx;
          font-family: SourceHanSansCN;
          font-weight: 400;
          color: #86858a;
          margin-bottom: 32rpx;
        }

        .openClose {
          width: 687rpx;
          height: 60rpx;
          background-color: #e4e4e4;
          border-radius: 30rpx;
          padding: 4rpx;
          // display: flex;
          // justify-content: space-around;
          .close_father {
            width: 336rpx;
            height: 58rpx;
            float: left;
            .close {
              width: 336rpx;
              height: 58rpx;
              background-color: #fff;
              border-radius: 30rpx;
              text-align: center;
              line-height: 58rpx;
              display: flex;
              justify-content: center;
              align-items: center;
              .fork {
                width: 22rpx;
                height: 22rpx;

                background: no-repeat center/100%
                  url("../../../static/icon/02-3grey_cross.png");
              }
            }
          }
          .close_father {
            position: relative;
            .circle {
              position: absolute;
              left: 50%;
              width: 28rpx;
              height: 27rpx;
              margin: 0 auto;
              margin-top: 15rpx;
              border: 3rpx solid #e4e4e4;
              border-radius: 28rpx;
            }
            .circleBorder {
              border: 3rpx solid #fff;
            }
            .open {
              width: 336rpx;
              height: 58rpx;
              background-color: #fff;
              border-radius: 30rpx;
              float: right;
            }
          }
        }
        .yellowbackground {
          background-color: #e2c93b;
        }
      }
      .footer {
        margin-top: 50rpx;
        .setDefault {
          display: flex;
          justify-content: space-between;
          margin-bottom: 90rpx;
        }
        .setButton {
          width: 686rpx;
          display: flex;
          justify-content: space-between;
          .uv-button-wrapper {
            width: 334rpx;
            height: 76rpx;
            color: #fff;
          }
          .confirmbutton {
            width: 50%;
            height: 76rpx;
            color: #fff;
          }
        }
      }
    }
  }
}

::v-deep .arrow-white {
  width: 48rpx;
  height: 49rpx;
  background-color: #fff;
  border-radius: 50rpx;
  background: no-repeat center/100%
    url("../../../static/icon/02-3white_plus.png");
}
::v-deep .arrow-right {
  width: 48rpx;
  height: 49rpx;
  background: no-repeat center/100%
    url("../../../static/icon/02-3yellow_plus.png");
}
::v-deep .uv-form-item__body__left {
  width: 150rpx !important;
  // background-color: red;
}
</style>
