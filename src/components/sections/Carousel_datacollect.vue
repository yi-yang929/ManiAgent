<script setup>
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Physical Experiments</h1>
    </el-row>

    <!-- 两个视频并排 -->
    <el-row justify="center" :gutter="20">
      <!-- 第一个视频 -->
      <el-col :xs="24" :sm="12">
        <el-container class="video-container">
          <video controls muted preload playsinline>
            <source src="./video/datacollection.mp4" type="video/mp4">
          </video>
          <div class="video-caption">Data collection process.</div>
        </el-container>
      </el-col>
      
      <!-- 第二个视频 -->
      <el-col :xs="24" :sm="12">
        <el-container class="video-container">
          <video controls muted preload playsinline>
            <source src="./video/cogact_carrot.mp4" type="video/mp4">
          </video>
          <div class="video-caption">Execution results of CogACT trained by auto collect data.</div>
        </el-container>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.video-container {
  margin: 20px 0;
  position: relative;
}

video {
  aspect-ratio: 16 / 9;
  width: 100%;
}

.video-caption {
  text-align: center;
  margin-top: 10px;
  font-size: 0.9em;
  color: #666;
}
</style>
