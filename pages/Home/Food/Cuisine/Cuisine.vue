<template>
  <view class="cuisine_container">
    <uv-input
      @focus="focus"
      @change="change"
      v-model="value"
      placeholder="搜索食物"
      prefixIcon="search"
      prefixIconStyle="font-size: 22px;color: #909399"
    ></uv-input>
    <!-- <uni-easyinput placeholder="请输入姓名" /> -->
    <view v-if="isSearch ? false : true" class="text_and_icon">
      <view class="text">历史搜索</view>
      <view class="icon"></view>
    </view>
    <view v-if="isSearch ? false : true" class="history">
      <view class="tag">
        <uv-tags
          size="large"
          borderColor="#fff"
          color="#989999"
          bgColor="#fff"
          text="馒头"
          shape="circle"
        ></uv-tags>
      </view>
      <view class="tag">
        <uv-tags
          size="large"
          borderColor="#fff"
          color="#989999"
          bgColor="#fff"
          text="包子"
          shape="circle"
        ></uv-tags>
      </view>

      <view class="tag">
        <uv-tags
          size="large"
          borderColor="#fff"
          color="#989999"
          bgColor="#fff"
          text="豆浆"
          shape="circle"
        ></uv-tags>
      </view>
    </view>
    <uv-list v-if="isSearch">
      <uv-list-item
        :clickable="true"
        @click="open"
        border="true"
        title="自定义内容1"
      ></uv-list-item>
      <uv-list-item border="true" title="自定义内容2"></uv-list-item>
      <uv-list-item border="true" title="自定义内容3"></uv-list-item>
    </uv-list>
    <uv-popup round="30" ref="popup" @change="open">
      <view class="popup_content">
        <uv-form>
          <uv-form-item label="牛奶" borderBottom>
            <uv-input placeholder="" border="none"> </uv-input>
            <template v-slot:right>
              <view class=""> 223千卡-1+ </view>
            </template>
          </uv-form-item>
          <uv-form-item label="牛奶" borderBottom>
            <uv-input placeholder="" border="none"> </uv-input>
            <template v-slot:right>
              <view class=""> 223千卡-1+ </view>
            </template>
          </uv-form-item>
        </uv-form>
      </view>
    </uv-popup>
  </view>
</template>

<script>
import uvForm from "../../../../uni_modules/uv-form/components/uv-form/uv-form.vue"
export default {
  components: { uvForm },
  data() {
    return {
      isSearch: false,
      SearchData: [],
      value: "",
    }
  },
  mounted() {
    this.$refs.popup.open("bottom")
  },
  methods: {
    open() {
      console.log("eee")
      this.$refs.popup.open("bottom")
    },
    focus() {
      //   this.$refs.popup.open("top")
    },
    change() {
      this.isSearch = true
    },
    show() {
      //   this.isSearch = true
    },
  },
}
</script>

<style lang="scss">
::v-deep .uv-list-item__wrapper {
  background-color: #efefef;
}
.cuisine_container {
  background-color: #efefef;
  padding: 30rpx;
  .text_and_icon {
    display: flex;
    justify-content: space-between;
    margin-top: 30rpx;
    margin-bottom: 30rpx;
    .text {
      font-size: 27rpx;
      font-family: SourceHanSansCN;
      font-weight: 500;
      color: #000000;
    }
    .icon {
      width: 31rpx;
      height: 31rpx;
      margin-top: 10rpx;
      background: no-repeat center/100%
        url("/static//icon/02-6-1-1green_bin.png");
    }
  }
  .history {
    display: flex;
    .tag {
      display: flex;
      width: 117rpx;
      height: 57rpx;
      margin-right: 18rpx;
    }
  }
  .popup_content {
    width: 750rpx;
    height: 499rpx;
    border-radius: 50rpx;
  }
}
</style>
