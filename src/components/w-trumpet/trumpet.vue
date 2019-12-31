<template>
  <div class="rollScreen_container" id="rollScreen_container">
    <div class="text">
      <img src="/static/images/laba.png" alt />
      <span>就买买最新活动</span>
    </div>
    <ul
      class="rollScreen_list"
      :style="{transform:transform}"
      :class="{rollScreen_list_unanim:num===0}"
    >
      <li class="rollScreen_once" v-for="(item,index) in contentArr" :key="index">
        <p
          style="font-size:12px; color:tomato; line-height:20px;"
          @click="goIntroduce(index)"
        >{{item.title}}</p>
      </li>
    </ul>
  </div>
</template>
 
<script>
export default {
  props: {
    height: {
      default: 20,
      type: Number
    },
    lineNum: {
      default: 5,
      type: Number
    }
  },
  data: function() {
    return {
      contentArr: [
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
        { title: "定制您专属的小程序" },
    
      ],
      num: 0
    };
  },
  computed: {
    transform: function() {
      return "translateY(-" + this.num * this.height + "px)";
    }
  },
  created: function() {
    let _this = this;
    setInterval(function() {
      if (_this.num !== _this.contentArr.length) {
        _this.num++;
      } else {
        _this.num = 0;
      }
    }, 3000);
  },
  methods: {
    goIntroduce(index) {
      // console.log(index);
      wx.redirectTo({
        url: "/pages/introduce/main?+index"
      });
    }
  }
};
</script>
 
<style>
.rollScreen_container {
  display: inline-block;
  /* position: relative; */
  overflow: hidden;
  height: 25px;
  width: 100%;
  border-top: 3px solid #f6f6f6;
}
.rollScreen_list {
  transition: 0.4s linear;
  line-height: 28px;
  margin-left: 140px;
}

.rollScreen_list_unanim {
  transition: none;
}
.text {
  margin-right: 40px;
  padding: 0 10px;
}
.text image {
  width: 20px;
  height: 20px;
  vertical-align: bottom;
  margin-right: 10px;
}
.text span {
  font-size: 12px;
  margin-top: 2px;
  color: rgb(255, 14, 14);
}
</style>