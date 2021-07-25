<template>
  <!-- 首页内容 -->
  <div class="main">
    <img :src="bgo" class="bgo" />
    <n-badge value="999+" class="ato">
      <n-avatar :src="vx" @click="handleAvatarClick" :size="100" circle></n-avatar>
    </n-badge>
    <!-- <n-badge :value="999" show-zero class="ato-title">
      <img :src="vx" alt="vx" class="ato" @click="handleAvatarClick" />
    </n-badge>-->
    <div class="main-wrapper">
      <div class="name">
        <n-gradient-text type="error">小宁鸽</n-gradient-text>
      </div>
      <div class="map">
        <n-gradient-text type="success">吉林·延边</n-gradient-text>
      </div>
      <div class="motto hitokoto">
        <n-gradient-text type="info">{{ hitokoto }}</n-gradient-text>
      </div>
    </div>
  </div>
</template>

<script setup>
import bgo from '../assets/images/bgo.jpg';
import vx from '../assets/images/vx.jpg';
import { NIcon, NGradientText, useMessage, NBadge, NAvatar } from 'naive-ui'
import { ref } from 'vue'
import axios from 'axios'
const hitokoto = ref('追逐梦想的人比抓住梦想的人更能发挥实力。')
axios.get('https://v1.hitokoto.cn/',)
  .then((result) => {
    console.log('result', result)
    let { data, status } = result;
    if (status === 200) {
      hitokoto.value = data.hitokoto
    } else {
      hitokoto.value = '获取粗错啦~'
    }
  })
  .catch(function (error) {
    console.log(error);
  });
const handleAvatarClick = () => {
  // message.info("戳我干嘛 ￣へ￣'")
}


</script>

<style lang="less" scoped>
.main {
  &-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    // margin-top: 75px;
    gap: 10px;
  }
}
.ato {
  position: absolute;
  left: 50%;
  top: 35%;
  z-index: 9;
  transform: translate(-50%, 0);
  ::v-deep(.n-badge-sup) {
    left: 80%;
    z-index: 9;
  }
}
.map {
  margin-top: 12px;
  text-align: center;
  font-weight: 300;
  i {
    display: inline-block;
    margin-right: 6px;
    margin-top: -2px;
    width: 16px;
    height: 16px;
    background-image: url(../images/map.svg);
    background-size: 100%;
    vertical-align: middle;
  }
}
.motto {
  margin: 0 auto;
  margin-top: 10px;
  width: 265px;
  height: 45px;
  line-height: 25px;
  text-align: center;
  font-size: 14px;
  ::v-deep(.n-gradient-text) {
    white-space: pre-wrap;
  }
}
</style>