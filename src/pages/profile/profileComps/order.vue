<template>
  <div class="info">
    <div class="me_info" @click="goInorder">
      <span class="text">我的订单</span>
      <span class="alltext">
        查看全部
        <img src="/static/icons/right-arrow.png" alt />
      </span>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    goInorder() {
      wx.navigateTo({
        url: "/pages/inorder/main"
      });
    }
  }
};
</script>
<style scoped>
.info {
  padding: 0 20rpx;
  margin-bottom: 10rpx;
  border-bottom: 10rpx solid #f6f6f6;
}
.me_info {
  display: flex;
  height: 80rpx;
  background: #fff;
}
.me_info span {
  flex: 1;
  line-height: 80rpx;
  color: #000;
}
.me_info .alltext {
  color: rgb(145, 137, 131);
  margin-left: 64%;
  font-size: 24rpx;
  line-height: 80rpx;
}
.me_info image {
  width: 26rpx;
  height: 26rpx;
  vertical-align: middle;
  margin-top: -4rpx;
}
.text {
  font-size: 26rpx;
}
</style>