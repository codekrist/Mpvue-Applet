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
      <swiper-item v-for="(item,index) in banners" :key="index">
        <img :src="item.picname" alt />
      </swiper-item>
    </swiper>
  </div>
</template>
<script>
import globalData from "@/global.js";
export default {
  data() {
    return {
      banners: []
    };
  },
  methods: {
    getType() {
      wx.request({
        url: globalData.api + "routes/carousel",
        success: res => {
          let result = res.data.data;
          for (let i = 0; i < result.length; i++) {
            //console.log( result[i].picname )
            result[i].picname = globalData.api + "upload/" + result[i].picname;
          }
          this.banners = result;
        }
      });
    }
  },
  created() {
    this.getType();
  }
};
</script>
<style lang="">
.swiper-box {
  /* height: 150px; */
  background: #e46352;
  background-image: -webkit-gradient(
    linear,
    left bottom,
    left top,
    from(#afa6a5),
    color-stop(50%, #e46352)
  );
  border-bottom-right-radius: 50%;
  border-bottom-left-radius: 50%;
  margin-bottom: 6px;
}
.swiper {
  padding: 0 10px;
  padding-top: 6px;
  border-radius: 6px;
  overflow: hidden;
}
.swiper image {
  height: 100%;
  width: 100%;
  border-radius: 6px;
}
</style>