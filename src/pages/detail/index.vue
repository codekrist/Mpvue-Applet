<template>
  <div class="swiper-box">
    <swiper
      class="swiper"
      indicator-dots="true"
      indicator-active-color="#fff"
      indicator-color="#ccc"
      autoplay="true"
      circular
      interval="3000"
    >
      <swiper-item v-for="item in banners" :key="item.id">
        <img :src="item.imgUrl" alt />
      </swiper-item>
    </swiper>
    <!-- 商品价钱 -->
    <div class="detail">
      <div class="prodect-detail">静候数载，《盗墓笔记》系列全新出版作品震撼上市！南派三叔亲撰写作心路序言，随书附赠精美印签明信片+藏书票书签。</div>
      <span class="price">￥123</span>
      <span class="oldprice">￥432</span>
    </div>
    <!-- 底部 -->
    <div class="tab-bottom">
        
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      banners: [
        { id: "01", imgUrl: "/static/banners/6d96b6d9f9ab5e03.jpg" },
        { id: "01", imgUrl: "/static/banners/aaa9b2b38f237592.jpg" },
        { id: "01", imgUrl: "/static/banners/f3be24501873c80c.jpg" },
        { id: "01", imgUrl: "/static/banners/q70.jpg" }
      ]
    };
  }
};
</script>
<style  scoped>
swiper {
  height: 350px;
  width: 100%;
}
.swiper image {
  width: 100%;
  height: 100%;
}
.detail {
  padding: 5px 20px;
  border-bottom: 4px solid #f6f6f6;
}
.prodect-detail {
  font-size: 14px;
  color: #969696;
}
.price {
  color: #e63720;
  font-size: 14px;
  margin-right: 30px;
}
.oldprice {
  color: #858282;
  text-decoration: line-through;
  font-size: 14px;
}
/* 底部 */
.tab-bottom{
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    height: 50px;
    background: rgb(197, 68, 68);
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.7)
}
</style>