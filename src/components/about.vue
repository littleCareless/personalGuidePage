<template>
  <div class="main">
    <img :src="bgt" class="bgt" />
    <img :src="vx" class="ats" />
    <div class="about-group">
      <div class="about">
        <p>
          > _酷爱前端开发，会去自学感兴趣的一切东西
          <br />> _略懂H5，喜欢折腾，努力去解决遇到的一切问题
        </p>
      </div>
      <div class="about">
        <p>
          这条路我才刚刚迈开了我的第一步
          <br />路上的坎一定会非常多，但
          <br />在我眼里
          <br />没有什么问题是尝试不能解决的，
          <br />即使前方的路看似绝境，也要有硬生生给自己开出一条路的勇气
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import bgt from '../assets/images/bgt.jpg';
import vx from '../assets/images/vx.jpg';
</script>

<style lang="less" scoped>
.about-group {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: center;
  align-items: center;
  height: 100%;
  gap: 30px;
  .about {
    margin: 0 40px;
    padding: 10px;
    border-radius: 15px;
    background: #ecf0f3;
    box-shadow: inset 5px 5px 10px #b1b4b6, inset -5px -5px 10px #fff;
    font-size: 12px;
  }
}
</style>