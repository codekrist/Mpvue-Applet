<template>
  <div>
    <div class="inorder">
      <ul class="all_inorder">
        <li>全部订单</li>
        <li>待付款</li>
        <li>待收货</li>
        <li>待评价</li>
      </ul>
    </div>
    <div class="img">
      <img src="/static/icons/nodingdan.png" alt />
      <p>您还没有订单</p>
    </div>
  </div>
</template>

<script>
export default {
  computed: {},
  methods: {}
};
</script>

<style>
.inorder {
  padding: 0 10px;
  box-shadow: 0 1px 0 rgba(146, 144, 144, 0.4);
}
.all_inorder {
  display: flex;
  text-align: center;
  height: 40px;
  line-height: 40px;
}
.all_inorder li {
  flex: 1;
  font-size: 14px;
}
.img {
  width: 100px;
  height: 100px;
  margin: 50px auto;
}
.img image {
  width: 100%;
  height: 100%;
}
.img p {
  line-height: 50px;
  text-align: center;
  font-size: 12px;
}
</style>
