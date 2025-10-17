<script lang="ts" setup>
import { ref, onMounted } from 'vue'

declare global {
  interface Window {
    gtag: (...args: any[]) => void
    dataLayer: any[]
  }
}

const initGoogleAnalytics = () => {
  // 创建并添加 Google Analytics 脚本
  const script = document.createElement('script')
  script.async = true
  script.src = 'https://www.googletagmanager.com/gtag/js?id=G-G5XG7F9BTR'
  document.head.appendChild(script)

  // 初始化 dataLayer
  window.dataLayer = window.dataLayer || [];
  
  // 定义 gtag 函数
  window.gtag = function(){window.dataLayer.push(arguments);}
  
  // 配置 GA
  window.gtag('js', new Date());
  window.gtag('config', 'G-G5XG7F9BTR');
}

// 页脚需要的链接
const links = {
    Nerfies: "https://github.com/nerfies/nerfies.github.io",
    Vue: "https://cn.vuejs.org/",
    Vite: "https://cn.vitejs.dev/",
    ElementPlus: "https://element-plus.org/zh-CN/",
    template: "https://github.com/JunyaoHu/academic-project-page-template-vue",
}

// onMounted(() => {
//   const script = document.createElement('script')
//   script.src = '//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'
//   document.body.appendChild(script)
// })

onMounted(() => {
  try {
    initGoogleAnalytics();
    const script = document.createElement('script')
    script.src = '//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'
    document.body.appendChild(script)
  } catch (error) {
    console.error('Failed to initialize Google Analytics:', error)
  }
})

</script>

<template>
  
  <div class="bg">
    
    <el-watermark :content="['YangYi', 'ManiAgent']" :gap="['60','0']" :z-index="0">
      <el-row justify="center">
        <p class="footer">
          This template is inspired by 
          <a :href="links.Nerfies">Nerfies</a>,<br/>
          
          powered by 
          <a :href="links.Vue">Vue</a>, 
          <a :href="links.Vite">Vite</a>, and
          <a :href="links.ElementPlus">Element Plus</a>.<br/>
          
          You can fork🛠️ / star✨/ PR📃 from <a :href="links.template">here</a>.
        </p>
      </el-row>
    </el-watermark>
  </div>
  <div class="visit-count">
    <span id="busuanzi_container_site_pv">
      Total visits: <span id="busuanzi_value_site_pv"></span> 
    </span>
  </div>
</template>



<style scoped>

/* 页脚背景 */
.bg {
  background-color: rgb(235, 235, 235);
}

/* 页脚文字 */
.footer {
  text-align: center;
  margin: 20px;
  z-index: 1;
}

.visit-count {
  text-align: center;
  padding: 20px 0;
  color: #666;
  font-size: 14px;
}

</style>