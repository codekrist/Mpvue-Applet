<template>
  <div class="icons" >
    <div class="icons-item" v-for="(item,index) in typeicons" :key="index" @click="goToClassify(item._id)">
      <img :src="item.picname" alt />
      <p>{{item.typename}}</p>
    </div>
  </div>
</template>
<script>
import globalData from "@/global.js";
export default {
  data() {
    return {
      typeicons: []
    };
  },
  methods: {
    getType() {
      wx.request({
        url: globalData.api + "routes/type",
        success: res => {
          let result = res.data.data;
          for (let i = 0; i < result.length; i++) {
            //console.log( result[i].picname )
            result[i].picname = globalData.api + "upload/" + result[i].picname;
          }
          this.typeicons = result;
        }
      });
    },
    // 跳转到calssify
    goToClassify(typeid){
      console.log(typeid)
      wx.navigateTo({
        url:'/pages/classify/main?typeid='+typeid
      })
    }
  },
  created() {
    this.getType();
  }
};
</script>
<style scoped>
.icons {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  background: #fff;
  padding: 5px 0;
}
.icons-item {
  display: flex;
  flex-direction: column;
  width: 20%;
  align-items: center;

  padding: 5px 0;
}
.icons-item p {
  font-size: 12px;
  padding-top: 4px;
  color: #000000;
}
.icons-item image {
  width: 40px;
  height: 40px;
}
</style>