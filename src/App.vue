<template>
 <div class="dark">
   <BlackHoleBackground class="h-[1000px] flex items-center justify-center custom-center-light">
     <div class="relative flex flex-col items-center justify-center gap-8 px-4 w-full max-w-4xl pt-0">
       <!-- 主標題區域 -->
       <Motion
         as="div"
         :initial="{ opacity: 0, y: 40, filter: 'blur(10px)' }"
         :while-in-view="{
           opacity: 1,
           y: 0,
           filter: 'blur(0px)',
         }"
         :transition="{
           delay: 0.1,
           duration: 0.3,
           ease: 'easeInOut',
         }"
         class="flex flex-col items-center justify-center gap-7"
       >
         <div class="sparkles-wrapper">
           <SparklesText
             text="2025 全薪升級"
             :colors="{ first: '#d2ac2f', second: '#f4d03f' }"
             :sparkles-count="10"
             class="text-6xl"
           />
         </div>
         
         <!-- 副標題 -->
         <div class="text-2xl md:text-4xl font-bold text-white text-center">
           帶你從零開始 打造高薪工程腦
         </div>
       </Motion>

       <!-- IconCloud -->
       <div class="grid place-content-center -mt-20">
         <IconCloud :images="imageUrls" 
           :slugs="slugs"
         />
       </div>

       <!-- 底部文字 - 靠近 IconCloud -->
       <div class="text-2xl md:text-4xl font-bold text-white text-center -mt-20">
         多學一語言 多賺一份錢
       </div>
     </div>
   </BlackHoleBackground>
 </div>
</template>

<style scoped>
.custom-center-light::after {
 background: radial-gradient(ellipse at 0% 0%, #d2ac2f 0%, transparent 50%) !important;
}

/* 只針對文字區域設定 */
.sparkles-wrapper {
 position: relative;
 z-index: 10;
}

.sparkles-wrapper :deep(.text-6xl) {
 color: #d2ac2f !important;
 filter: none !important;
}

/* 降低背景混合模式強度 */
.custom-center-light :deep(.mix-blend-overlay) {
 opacity: 0 !important;
}

/* 或者針對特定的混合模式層 */
.custom-center-light :deep(.mix-blend-overlay) {
 opacity: 0 !important;
}
</style>

<script setup lang="ts">
import { Motion } from "motion-v";
import BlackHoleBackground from './components/ui/bg-black-hole/BlackHoleBackground.vue';
import SparklesText from './components/ui/sparkles-text/SparklesText.vue';
import IconCloud from './components/ui/icon-cloud/IconCloud.vue';

const slugs = [
 "typescript",
 "javascript",
 "postman",
 "c++",
 "react",
 "createreactapp",
 "android",
 "html5",
 "css",
 "nodedotjs",
 "ollama",
 "nextdotjs",
 "prisma",
 "Anaconda",
 "postgresql",
 "firebase",
 "nginx",
 "vercel",
 "testinglibrary",
 "p5dotjs",
 "cypress",
 "docker",
 "git",
 "jira",
 "github",
 "gitlab",
 "vuedotjs",
 "androidstudio",
 "n8n",
 "figma",
 "openai",
 "codepen",
 "python",
 "mysql",
];

const imageUrls = slugs.map((slug) => `https://cdn.simpleicons.org/${slug}/${slug}`);

</script>