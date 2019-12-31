<template>
  <div>
    <!-- 顶部搜索框 -->
    <Headers />

    <!-- 展示轮播图 -->
    <swipers />
    <!-- 展示分类图标 -->
    <Icons />
    <!-- 喇叭区 -->
    <Video />
    <Trumpet />
    <!-- 活动区 -->

    <Activity />
    <!-- 精品推荐区 -->

    <Recommends />
  </div>
</template>

<script>
import Headers from "@/components/w-header/header";
import swipers from "@/components/w-swiper/swipers";
import Icons from "./homeComps/icons";
import Trumpet from "@/components/w-trumpet/trumpet";
import Activity from "./homeComps/activity";
import Recommends from "./homeComps/recommend";
import Video from './homeComps/video'
export default {
  components: { Headers, swipers, Icons, Trumpet, Activity, Recommends ,Video},
  data() {
    return {};
  },

  methods: {},

  created() {}
};
</script>

<style scoped>
.swiper image {
  width: 100%;
  height: 100%;
}
</style>
