<template>
  <view class="ranking_container">
    <view class="ranking_content">
      <view class="ranking_title">
        <view class="isSelect title ranking_title_1"> 班级排名</view>
        <view class="title ranking_title_2"> 学校排名</view>
        <view class="title ranking_title_3">区域排名 </view>
      </view>
    </view>
    <view class="integral">
      <text>积分</text>
    </view>
    <view class="ranking_list">
      <uv-list>
        <uv-list-item
          title="思思"
          thumb="/static/icon/02-4trophy_blue.png"
          thumb-size="lg"
          rightText="100"
          border="true"
        >
        </uv-list-item>
        <uv-list-item
          title="思思"
          thumb="/static/icon/02-4trophy_green.png"
          thumb-size="lg"
          rightText="100"
          border="true"
        >
        </uv-list-item>
        <uv-list-item
          title="思思"
          thumb="/static/icon/02-4trophy_yellow.png"
          thumb-size="lg"
          rightText="100"
          border="true"
        >
        </uv-list-item>
      </uv-list>
    </view>
  </view>
</template>
<script>
export default {
  data() {
    return {
      list: ["未付款", "待评价", "已付款"],
      // 或者如下，也可以配置keyName参数修改对象键名
      // list: [{name: '未付款'}, {name: '待评价'}, {name: '已付款'}],
      current: 1,
      blueImage: "",
    }
  },
  methods: {
    change(index) {
      this.current = index
    },
  },
}
</script>

<style lang="scss">
page {
  height: 100%;
  background-color: #efefef;
  overflow: hidden;
}
.ranking_container {
  height: 100%;
  //   background-color: #fff;
  .ranking_content {
    height: 120rpx;
    background-color: #fff;
    overflow: hidden;
    .ranking_title {
      margin-top: 27rpx;
      display: flex;
      justify-content: space-around;
      background-color: #fff;
      .title {
        width: 200rpx;
        height: 70rpx;
        background-color: #e9e9eb;
        border-radius: 70rpx;
        text-align: center;
        line-height: 70rpx;
        font-size: 20rpx;
        font-family: SourceHanSansCN;
        font-weight: 400;
        color: #ffffff;
      }
      .isSelect {
        background-color: #279da9;
      }
    }
  }
  .integral {
    background-color: #fff;
    width: 100%;
    height: 50rpx;
    text {
      float: right;
    }
  }
}
.ranking_list {
  // padding: 10rpx;
}
</style>
