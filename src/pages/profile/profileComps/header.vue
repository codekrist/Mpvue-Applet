<template>
  <div>
    <div class="header">
      <div class="avatar">
        <image src="/static/icons/touxiang.png" />
      </div>
      <!-- <div class="login-info">
        <div class="login">登录/注册</div>
        <div class="phone">
          <image src="/static/icons/shouji.png" />暂无绑定手机号
        </div>
      </div>'-->
      <div class="arrow">
        <!-- <image src="/static/icons/right-arrow.png" /> -->
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.header {
  position: relative;
  display: flex;
  background: linear-gradient(to top, rgb(235, 189, 159), #e46352);
  height: 170rpx;
  padding: 12rpx 30rpx;
  color: #fff;
}
.avatar {
  margin: 0 auto;
}
.avatar image {
  width: 140rpx;
  height: 140rpx;
  border-radius: 50%;

  /* background: #f2f2f2;
  vertical-align: middle; */
}

.login-info {
  vertical-align: middle;
  margin-left: 30rpx;
}

.login-info .login {
  font-size: 36rpx;
  margin-top: 18rpx;
}

.login-info .phone {
  font-size: 28rpx;
  margin-top: 10rpx;
}

.phone image {
  width: 34rpx;
  height: 34rpx;
  vertical-align: middle;
  position: relative;
  bottom: 4rpx;
}

.arrow {
  position: absolute;
  right: 30rpx;
  margin-top: 30rpx;
}

.arrow image {
  width: 60rpx;
  height: 60rpx;
  color: #f8f8f8;
}
</style>