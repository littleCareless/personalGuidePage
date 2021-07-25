<template>
  <div class="wrapper">
    <section class="left"></section>
    <div class="right">
      <div class="right-wrapper">
        <div class="container">
          <div class="hander">
            <nav id="nav-menu">
              <n-button
                type="text"
                href="#"
                data-rel="home-me-section"
                :class="{ active: componentId === item.value }"
                v-for="item in nav"
                :key="item.value"
                @click="handleNavClick(item.value)"
              >{{ item.label }}</n-button>
            </nav>
          </div>
          <div class="content">
            <!-- <transition name="fade" mode="out-in" appear> -->
            <component :is="componentId"></component>
            <!-- </transition> -->
          </div>
          <div class="footer">
            <!-- 微信 -->
            <a href="#" target="_blank">
              <n-icon size="18" :depth="1">
                <LogoWechat />
              </n-icon>
            </a>
            <!-- Github -->
            <a href="https://github.com/littleCareless" target="_blank">
              <n-icon size="18" :depth="1">
                <LogoGithub />
              </n-icon>
            </a>
            <!-- 邮箱 -->
            <a href="#" target="_blank">
              <n-icon size="18" :depth="1">
                <MailOpen />
              </n-icon>
            </a>
            <!-- 内容结束 -->
          </div>
        </div>
      </div>
      <div class="right-footer">
        <span>
          <span>© 2021</span>
          <a href="http://beian.miit.gov.cn" target="_blank" title>吉ICP备19005472号-2</a>
        </span>
      </div>
    </div>
    <!-- 主体结束 -->
    <!-- 右下角国旗 -->
    <a href="https://www.gov.cn/" target="_blank" class="flag">
      <img :src="chinaSvg" />
    </a>
    <n-back-top :right="100" />
  </div>
  <!--wrapper-->
  <!-- <div id="tp-weather-widget"></div> -->
</template>
<script>
export default {
  name: 'app',
}
</script>
<script setup>
import { MapSharp, LogoWechat, LogoGithub, MailOpen } from '@vicons/ionicons5'
import chinaSvg from './assets/images/China.svg'
import about from './components/about.vue'
import home from './components/home.vue'
import course from './components/course.vue'
import website from './components/website.vue'
import { defineComponent, reactive, toRefs, ref } from 'vue'
import { NBackTop, NButton, NIcon } from 'naive-ui'

const componentId = ref(home);
const nav = ref([
  {
    label: '首页',
    value: home
  },
  {
    label: '关于',
    value: about
  },
  {
    label: '历程',
    value: course
  },
  {
    label: '站点',
    value: website
  }
])
const handleNavClick = (val) => {
  componentId.value = val
}
</script>

<style lang="less" >
@import "./index.less";
.right {
  .right-footer {
    margin: 0 auto;
    padding: 20px 50px;
    width: 100%;
    background: #f5f5f5;
    font-size: 12px;
    color: #555;
    p {
      margin: 0;
      color: #555;
    }
    p span {
      margin-right: 5px;
    }
  }
}
.right {
  overflow: auto;
  width: 50%;
  height: 100%;
  max-height: 100%;
  &-wrapper {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-content: space-between;
    align-items: center;
    height: 100%;
  }
}
.flag {
  position: fixed;
  right: 15px;
  bottom: -10px;
  width: 60px;
}
nav {
  display: flex;
  justify-content: space-around;
  button {
    --height: 30px !important;
  }
  button.active {
    .n-button__content {
      color: #71b3dd;
    }
  }
}
.navo {
  display: inline-flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  align-items: center;
  margin-top: 20px;
  width: 100%;
  text-align: center;
  gap: 30px;
  a {
    transition: 0.5s;
    animation: light 4s ease-in-out infinite;
    &:hover {
      transform: scale(1.15) rotate(720deg);
    }
  }
}
</style>