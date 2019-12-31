<template>
  <div class="recommend">
    <!-- 精选商品 -->
    <div class="product">
      <div class="product-item" v-for="(item,index) in productItem" :key="index">
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
    return {
      productItem: []
    };
  },

  methods: {
    //1- 获取后台商品数据
    getProduct() {
      wx.request({
        url: globalData.api + "routes/product",
        success: res => {
          // console.log(res);
          let result = res.data.data;
          for (let i = 0; i < result.length; i++) {
            //console.log( result[i].picname )
            result[i].picname = globalData.api + "upload/" + result[i].picname;
          }
          this.productItem = result;
        }
      });
    },
    //2- 点击商品跳转到详情页面
    goDetail(_id) {
      wx.navigateTo({
        url: "/pages/detail/main?_id=" + _id
      });
    }
  },
  created() {
    this.getProduct();
  }
};
</script>
<style scoped>
.recommend {
  background: #f6f6f6;
}

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