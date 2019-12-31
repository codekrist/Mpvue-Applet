<template>
  <div>
    <div class="cart">
      <div class="cart_img">
        <p class="img_p">
          <img src="/static/tabs/cart.png" alt />
        </p>
        <p>购物车还是是空的</p>
        <p class="p_box" @click="goHome">去逛逛</p>
      </div>

      <!-- 猜你喜欢 -->
      <div class="guess-like">
        <span class="line"></span>
        <span class="cirlce"></span>
        <span class="text">&nbsp;猜 你 喜 欢 &nbsp;</span>
        <span class="cirlce"></span>
        <span class="line"></span>
      </div>
    </div>
    <!-- 猜你喜欢商品 -->
    <div class="product">
      <div class="product-item" v-for="(item,index) in guessItem" :key="index">
        <i>
          <img :src="item.picname" alt @click="goDetail(item._id)" />
        </i>

        <p class="detail">
          <span class="title">【{{item.title}}】</span>
          {{item.detail}}
        </p>
        <span class="price">￥{{item.price}}</span>
        <!-- <span class="price old">￥{{item.oldprice}}</span> -->
        <!-- <p class="like">{{item.like}}</p> -->
      </div>
    </div>
  </div>
</template> 

<script>
import globalData from "@/global.js";
export default {
  data() {
    return { guessItem: [] };
  },
  onLoad(options) {
    // console.log(this.$root.$mp.query, 1122); //{}1122
  },

  methods: {
    goHome() {
      console.log(222);
      wx.reLaunch({
        url: "/pages/home/main"
      });
    },
    goDetail(_id) {
      wx.navigateTo({
        url: "/pages/detail/main?_id=" + _id
      });
    },
    //------------------------
    //1- 获取后台商品数据
    getProduct() {
      wx.request({
        url: globalData.api + "routes/guess",
        success: res => {
          console.log(res);
          let result = res.data.data;
          for (let i = 0; i < result.length; i++) {
            //console.log( result[i].picname )
            result[i].picname = globalData.api + "upload/" + result[i].picname;
          }
          this.guessItem = result;
        }
      });
    }
  },
  created() {
    console.log("我是小草帽小程序初始化成功");
    this.getProduct();
  }
};
</script>

<style scoped>
.cart_img {
  margin: 80px auto 0;
  width: 200px;
  height: 200px;
  font-size: 14px;
  text-align: center;
  margin-bottom: 80px;
}
.cart_img .img_p {
  width: 55px;
  height: 55px;
  margin: 40px auto 10px;
}
.cart_img .img_p img {
  width: 100%;
  height: 100%;
}
/* 猜你喜欢 */
.guess-like {
  height: 30px;
  font-size: 14px;
  text-align: center;
  line-height: 30px;
  margin-bottom: 4px;
  border-top: 4px solid #f6f6f6;
}
.text {
  color: rgb(218, 126, 7);
}
.p_box {
  background: #e46352;
  border-radius: 8px;
  color: #fff;
  width: 80px;
  margin: 10px auto;
  padding: 5px;
  font-size: 12px;
}
.cirlce {
  display: inline-block;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: rgb(184, 102, 9);
  vertical-align: middle;
}
.line {
  display: inline-block;
  width: 40px;
  height: 1px;
  background: rgb(218, 126, 7);
  vertical-align: middle;
}
/*  ----------------------------------------*/
.product {
  display: flex;
  padding: 0 10px;
  flex-wrap: wrap;
  justify-content: space-between;
  background: #f6f6f6;
}
.product-item {
  width: 175px;
  background: #fff;
  border-radius: 6px;
  margin: 2px 0;
}
.product-item i {
  width: 100%;
  height: 180px;
}
.product-item image {
  width: 100%;
  height: 100%;
  vertical-align: middle;
  border-radius: 6px;
}

/* 新价格 */
.product-item .price {
  font-size: 12px;
  color: #e63720;
  margin-right: 8px;
  margin-left: 8px;
}
/* 旧价格 */
.product-item .old {
  text-decoration: line-through;
  color: #858282;
}
.product-item .title {
  font-size: 12px;
  color: #a11e0c;
}
.product-item .detail {
  font-size: 12px;
  height: 34px;
  padding: 0 8px;
  margin-top: 6px;
  color: #000000;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  overflow: hidden;
  overflow: hidden;
  text-overflow: ellipsis;
  word-break: break-all;
  display: -webkit-box;
  -webkit-line-clamp: 2; /* 行数*/
  -webkit-box-orient: vertical;
}
.product-item .like {
  height: 20px;
  width: 60px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 12px;
  text-align: center;
  line-height: 20px;
  color: rgb(24, 23, 23);
  box-shadow: 0 0 2px rgba(238, 218, 218, 0.7);
  margin-left: 100px;
  margin-bottom: 4px;
}
</style>
