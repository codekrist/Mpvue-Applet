<template>
  <div>
    <div class="activity">
      <div class="A-activity">
        <div class="lft">
          <p class="xs">限时抢购</p>
          <p class="distance">{{actEndTime}}</p>
          <div class="time">
            <span class="h">{{h}}</span>:
            <span class="m">{{m}}</span>:
            <span class="s">{{s}}</span>
          </div>
        </div>
        <div class="rig red">
          <img src="/static/images/00c62d8e389d750d.jpg" alt />
          <img src="/static/images/fb1b08dcbc561693.jpg" alt />
        </div>
      </div>
      <div class="A-activity">
        <div class="lft">
          <p class="xs jr">精品服饰</p>
          <div class="time">
            <!-- <span class="h">02</span>:
            <span class="m">12</span>:
            <span class="s">56</span>-->
          </div>
        </div>
        <div class="rig blue">
          <img src="/static/images/191126_89f8026c39ikdbba1f4ba895afcb0_800x800.jpg" alt />
          <img src="/static/images/191027_1d3hcake8jid3fh9h65ek95k121i4_640x960.png" alt />
        </div>
      </div>
    </div>
    <div class="activity">
      <div class="A-activity">
        <div class="lft">
          <p class="xs jj">名牌专区</p>
          <div class="time">
            <!-- <span class="h">{{h}}</span>:
            <span class="m">{{m}}</span>:
            <span class="s">{{s}}</span>-->
          </div>
        </div>
        <div class="rig tomato">
          <img src="/static/images/00c62d8e389d750d.jpg" alt />
          <img src="/static/images/fb1b08dcbc561693.jpg" alt />
        </div>
      </div>
      <div class="A-activity">
        <div class="lft">
          <p class="xs hd">9.9包邮</p>
          <div class="time"></div>
        </div>
        <div class="rig pink">
          <img src="/static/images/00c62d8e389d750d.jpg" alt />
          <img src="/static/images/fb1b08dcbc561693.jpg" alt />
        </div>
      </div>
    </div>
    <!--  -->
    <div class="guess-like">
      <span class="line"></span>
      <span class="cirlce"></span>
      <span class="text">&nbsp;为 你 推 荐 &nbsp;</span>
      <span class="cirlce"></span>
      <span class="line"></span>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      h: "00",
      m: "00",
      s: "00",
      actEndTime: "2019-12-15 13:50:00"
    };
  },
  created() {
    this.countDown();
  },

  methods: {
    timeFormat(param) {
      return param < 10 ? "0" + param : param;
    },
    countDown() {
      var interval = setInterval(() => {
        // 获取当前时间，同时得到活动结束时间数组
        let newTime = new Date().getTime(); // 对结束时间进行处理渲染到页面
        let endTime = new Date(this.actEndTime).getTime();
        let obj = null; // 如果活动未结束，对时间进行处理
        if (endTime - newTime > 0) {
          let time = (endTime - newTime) / 1000; // 获取天、时、分、秒

          let hou = parseInt((time % (60 * 60 * 24)) / 3600);
          let min = parseInt(((time % (60 * 60 * 24)) % 3600) / 60);
          let sec = parseInt(((time % (60 * 60 * 24)) % 3600) % 60);
          obj = {
            hou: this.timeFormat(hou),
            min: this.timeFormat(min),
            sec: this.timeFormat(sec)
          };
        } else {
          // 活动已结束，全部设置为'00'
          obj = {
            hou: "00",
            min: "00",
            sec: "00"
          };
          clearInterval(interval);
        }
        this.h = obj.hou;
        this.m = obj.min;
        this.s = obj.sec;
      }, 1000);
    }
  }
};
</script>
<style scoped>
.activity {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  padding: 0 10px;
  box-sizing: border-box;
  border-top: 4px solid #f6f6f6;
  background: #f6f6f6;
}
.A-activity {
  position: relative;
  flex: 1;
  height: 80px;
  background: #fff;
  border-radius: 4px;
  margin-right: 2px;
}
.lft {
  width: 90px;
  margin-top: 20px;
}
.distance {
  display: none;
}
.xs {
  text-align: center;
  background: linear-gradient(to right, rgb(224, 11, 153), rgb(233, 38, 4));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 800;
}
.jr {
  text-align: center;
  background: linear-gradient(to right, rgb(228, 175, 126), rgb(231, 91, 26));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 800;
}
.jj {
  text-align: center;
  background: linear-gradient(to right, rgb(219, 152, 51), rgb(240, 40, 4));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 800;
}
.hd {
  text-align: center;
  background: linear-gradient(to right, rgb(224, 104, 214), rgb(202, 7, 24));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 800;
}
.time {
  text-align: center;
  font-weight: 500;
}
.time span {
  display: inline-block;
  width: 15px;
  height: 15px;
  background: rgba(24, 18, 18, 0.7);
  color: #fff;
  font-size: 12px;
  text-align: center;
  line-height: 15px;
}
.time .m {
  margin-right: 5px;
}
.h {
  margin-right: 5px;
}
.red {
  background: linear-gradient(to right, rgb(223, 221, 221), #f3b1e8);
}
.blue {
  background: linear-gradient(to right, rgb(190, 179, 78), #cc711b);
}
.tomato {
  background: linear-gradient(to right, rgb(192, 163, 82), #f73e05);
}
.pink {
  background: linear-gradient(to right, rgb(253, 171, 171), #f1c4ea);
}
.rig {
  position: absolute;
  right: 4px;
  top: 20px;
  width: 78px;
  height: 40px;
  display: flex;

  padding: 10px 5px 6px 6px;
}
.rig image {
  width: 100%;
  height: 100%;
  flex: 1;
  margin-right: 4px;
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
  color: rgb(21, 120, 235);
  margin-right: 0;
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
  background: rgb(21, 120, 235);
  vertical-align: middle;
}
.line {
  display: inline-block;
  width: 40px;
  height: 1px;
  background: rgb(21, 120, 235);
  vertical-align: middle;
}
</style>