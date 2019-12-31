<template>
  <div class="about">
    <div class="y dizhi">
      <span>地址管理</span>
      <span class="dw">
        <img src="/static/icons/right-arrow.png" alt />
      </span>
    </div>
    <div class="y kefu">
      <span>客服微信 
         <i> LINAiTa999</i></span>

      <span class="dw">
        <img src="/static/icons/right-arrow.png" alt />
      </span>
    </div>
    <div class="y guanyu">
      <span>关于商城</span>
      <span class="dw">
        <img src="/static/icons/right-arrow.png" alt />
      </span>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.about {
  position: relative;
  margin-top: 10rpx;
}
.about div {
  display: flex;
  height: 30rpx;
  padding: 20rpx;
  font-size: 28rpx;
  border-bottom: 4rpx solid #f6f6f6;
  padding-left: 20rpx;
}
.about div span {
  flex: 1;
}
.about div span image {
  width: 26rpx;
  height: 26rpx;
  vertical-align: middle;
  margin-top: -4rpx;
}
.dw {
  position: absolute;
  right: 20rpx;
  /* background: pink; */
  /* margin-left: 80%; */
}
i{
    display: inline-block;
    font-size: 12px;
    color: #776a6a;
    padding-left: 20rpx;
}
</style>