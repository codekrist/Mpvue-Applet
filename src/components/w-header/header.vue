<template>
  <div class="header">
    <div class="center" @click="searchClick">
      <form action="/pages/cart">
        <div class="content">
          <img src="/static/icons/h-search.png" alt />
          <div class="h-text">优多买</div>
        </div>
      </form>
    </div>
    <div class="right">
      <p>登录</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    searchClick() {
      console.log("进入搜索页");
      // 点击跳转到搜索页
      wx.navigateTo({
        url: "/pages/search/main"
      });
    },
  }
};
</script>

<style>
.header {
  display: flex;
  height: 40px;
  background: #e46352;
  padding-left: 8px;
}

.right {
  position: relative;
  width: 40px;
}
.center {
  flex: 1;
  background: #fff;
  border-radius: 18px;
  height: 32px;
  margin-top: 4px;
  padding: 0 10px;
}
.left image {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 20px;
  height: 18px;
  text-align: center;
}
.right p {
  line-height: 40px;
  text-align: center;
  font-size: 14px;
  color: #fff;
}

.content image {
  height: 20px;
  width: 20px;
  margin-top: 6px;
  float: left;
}
.content .h-text {
  font-size: 14px;
  color: #000;
  float: left;
  margin-left: 10px;
  line-height: 32px;
}
</style>
