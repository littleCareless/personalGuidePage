<template>
  <div class="main">
    <img :src="bgt" class="bgt" />
    <img :src="vx" class="ats" />
    <div class="flex-content">
      <div class="web">
        <a href="#" target="_blank">站点1</a>
      </div>
      <!-- 站点一 -->
      <div class="web">
        <a href="#" target="_blank">站点1</a>
      </div>
      <!-- 站点二 -->
      <div class="web">
        <a href="#" target="_blank">站点1</a>
      </div>
      <div class="web">敬请期待</div>
      <div class="tips">所有站点均正常运行</div>
    </div>
  </div>
</template>

<script setup>
import bgt from '../assets/images/bgt.jpg';
import vx from '../assets/images/vx.jpg';
</script>

<style lang="less" scoped>
.flex-content {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  align-content: center;
  align-items: center;
  gap: 10px;
}
</style>