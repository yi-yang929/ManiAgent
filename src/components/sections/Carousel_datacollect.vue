<script setup>
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Automatic Data Collection</h1>
    </el-row>

    <!-- 两个视频并排 -->
    <el-row justify="center" :xs="24" :sm="20" :md="16" :lg="12" :xl="10">
      <!-- 第一个视频 -->
      <el-col :xs="24" :sm="10" :md="8" :lg="6" :xl="5">
        <el-container class="video-container">
          <h2 class="video-caption">Data collection process</h2>
          <video controls muted preload playsinline>
            <source src="/video/datacollection.mp4" type="video/mp4">
          </video>
        </el-container>
      </el-col>
      
      <!-- 第二个视频 -->
      <el-col :xs="24" :sm="10" :md="8" :lg="6" :xl="5">
        <el-container class="video-container">
          <h2 class="video-caption">Execution results of CogACT trained by auto collect data</h2>
          <video controls muted preload playsinline>
            <source src="/video/cogact_carrot.mp4" type="video/mp4">
          </video>
        </el-container>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.video-container {
  margin: 20px 0;
  position: relative;
  height: 100%;
  display: flex;
  flex-direction: column;
}

video {
  aspect-ratio: 16 / 9;
  width: 100%;
  object-fit: cover;
}

.video-caption {
  text-align: center;
  margin-bottom: 10px;
  font-size: 1.2em;
  color: #333;
  font-weight: 600;
  height: 3.6em; /* 使用固定高度替代min-height */
  line-height: 1.2em; /* 设置行高以确保多行文本居中 */
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden; /* 防止文本溢出 */
}
</style>
