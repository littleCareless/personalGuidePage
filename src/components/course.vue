<template>
  <div class="main">
    <img :src="bgt" class="bgt" />
    <img :src="vx" class="ats" />
    <div class="box">
      <div id="boxs">
        <div class="track-list">
          <!-- 时间轴开始 -->
          <n-timeline>
            <n-timeline-item content="啊" />
            <n-timeline-item type="success" title="成功" content="哪里成功" time="2018-04-03 20:46" />
            <n-timeline-item type="error" content="哪里错误" time="2018-04-03 20:46" />
            <n-timeline-item type="warning" title="警告" content="哪里警告" time="2018-04-03 20:46" />
            <n-timeline-item type="info" title="信息" content="是的" time="2018-04-03 20:46" />
          </n-timeline>
        </div>
        <!-- 时间轴结束 -->
      </div>
    </div>
    <div class="tip">注: 上下滑动查看历史进程</div>
  </div>
</template>

<script setup>
import bgt from '../assets/images/bgt.jpg';
import vx from '../assets/images/vx.jpg';
import { NTimeline, NTimelineItem } from 'naive-ui'
</script>

<style lang="less" scoped>
.tip {
  text-align: center;
  font-size: 12px;
  color: #aaa;
}
#boxs {
  overflow-x: hidden;
  overflow-y: scroll;
  margin: 0;
  height: 200px;
}
#boxs::-webkit-scrollbar {
  width: 5px;
  height: 5px;
}
#boxs::-webkit-scrollbar-track {
  border-radius: 12px;
  background-color: #eee;
}
#boxs::-webkit-scrollbar-thumb {
  border-radius: 12px;
  background-color: #aaa;
}
</style>