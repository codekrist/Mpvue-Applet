<template>
  <div class="bg-fff">
    <!-- 顶部搜索 -->
    <div class="search">
      <div class="center">
        <img class="S-img" src="/static/icons/h-search.png" alt />
        <div class="S-form">
          <form action>
            <input type="text" placeholder="我是小草帽" />
          </form>
        </div>
      </div>
      <div class="right">
        <p>搜索</p>
      </div>
    </div>
    <!-- 热门搜索 -->
    <div class="hot-search">
      <span class="hot-text">热门搜索</span>
      <span class="hide">隐藏</span>
    </div>
    <div class="search-more">
      <p class="red">拼装模型</p>
      <p class="red">小草帽</p>
      <p class="red">我是小草帽</p>
      <p>小草帽</p>
      <p>我是小草帽</p>
      <p>对讲机</p>
      <p>就买卖</p>
      <p>我是小草帽</p>
      <p>我是小草帽</p>
    </div>
  </div>
</template>
<script>
export default {
  methods: {},
  onLoad() {
    console.log("进入搜索框界面");
  }
};
</script>
<style scoped>
page {
  height: 100%;
  background: pink;
}
/* .bg-fff {
  background: #fff;
} */
/* 顶部搜索 */
.search {
  display: flex;
  height: 40px;
  box-shadow: 1px 0 1px rgba(100, 100, 100, 0.6);
  /* margin-bottom: 10px; */
  padding: 0 20px;
  /* background: #fff; */
}
.left,
.right {
  position: relative;
  width: 50px;
  /* background: #fff; */
}
.left image {
  position: absolute;
  left: 45%;
  top: 50%;
  transform: translate(-60%, -50%);
  width: 20px;
  height: 18px;
}
.center {
  flex: 1;
  position: relative;
}
.right p {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 40px;
  height: 26px;
  line-height: 26px;
  background: #e93b3d;
  border-radius: 4px;
  text-align: center;
  font-size: 12px;
  color: #fff;
}
.center .S-form {
  /* width: 100%; */
  height: 32px;
  background: #f6f6f6;
  margin-top: 4px;
  border-radius: 18px;
}
.center .S-form input {
  padding: 0 40px;
  font-size: 12px;
  color: #000000;
  line-height: 32px;
  /* background: pink; */
  padding-top: 4px;
}
.S-img {
  position: absolute;
  top: 11px;
  left: 10px;
  width: 18px;
  height: 18px;
}
/* 热门推荐 */
.hot-search {
  padding: 0 20px;
  overflow: hidden;
  margin: 8px 0;
  /* background: #fff; */
}
.hot-search .hot-text {
  float: left;
  font-size: 16px;
}
.hot-search .hide {
  float: right;
  font-size: 14px;
  color: #686868;
}
/* 搜索内容 */
.search-more {
  padding: 0 20px;
  color: #686868;
  height: 100px;
  height: 100px;
  /* background: #fff; */
}
.search-more p {
  background: #f6f6f6;
  float: left;
  font-size: 12px;
  /* margin-left: 8px; */
  margin-right: 10px;
  margin-bottom: 8px;
  padding: 4px 12px;
  border-radius: 4px;
}
/* 选中颜色 */
.red {
  color: #e93b3d;
}
</style>
