<template>
  <div>
    <!--  -->
    <Headers />
    <Info />
    <Order />
    <Wait />
    <Abouts />
  </div>
</template>

<script>
import Headers from "./profileComps/header";
import Info from "./profileComps/info";
import Order from "./profileComps/order";
import Wait from "./profileComps/wait";
import Abouts from "./profileComps/about";
export default {
  components: {
    Headers,
    Info,
    Order,
    Wait,
    Abouts
  },

  data() {
    return {};
  },

  created() {}
};
</script>

<style scoped>
</style>
