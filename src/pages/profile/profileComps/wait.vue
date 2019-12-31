<template>
  <div>
    <div class="wait">
      <!-- 快递信息 -->
      <ul class="wait_ul">
        <li>
          <img src="/static/icons/fukuan.png" alt />
          <p>待付款</p>
        </li>
        <li>
          <img src="/static/icons/fahuo.png" alt />
          <p>待发货</p>
        </li>
        <li>
          <img src="/static/icons/shouhuo.png" alt />
          <p>待收货</p>
        </li>
        <li>
          <img src="/static/icons/pingjia.png" alt />
          <p>待评价</p>
        </li>
        <li>
          <img src="/static/icons/tuikuan.png" alt />
          <p>退款/售后</p>
        </li>
      </ul>
      <!--  -->
    </div>
    <div class="b_img">
      <img src="/static/images/timg.jpg" alt />
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.wait {
  padding: 0 20rpx;
  border-bottom: 8rpx solid #f6f6f6;
  /* margin-bottom: 8rpx; */
}
.wait_ul {
  display: flex;
}
.wait_ul li {
  flex: 1;
  text-align: center;
  font-size: 24rpx;
  line-height: 40rpx;
  padding-bottom: 6rpx;
  color: rgb(78, 80, 82);
}
.wait_ul li image {
  width: 70rpx;
  height: 70rpx;
}
.b_img {
  height: 150rpx;
  width: 100%;
  border-radius: 10rpx;
  padding: 0 20rpx;
  box-sizing: border-box;
}
.b_img image {
  width: 100%;
  height: 100%;
  border-radius: 10rpx;
}
</style>