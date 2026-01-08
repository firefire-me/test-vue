<template>
  <div class="poem-container">
    <article class="poem-card">
      <header class="poem-header">
        <h1 class="poem-title">将进酒</h1>
        <div class="poem-meta">
          <span class="dynasty">朝代：唐朝</span>
          <span class="author">作者：李白</span>
        </div>
      </header>

      <main class="poem-content">
        <div
          class="verse"
          v-for="(verse, index) in verses"
          :key="index"
          :class="{ animated: true, delay: index }"
        >
          {{ verse }}
        </div>
      </main>
    </article>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

defineProps<{ msg: string }>();

const verses = ref([
  "君不见黄河之水天上来，奔流到海不复回。",
  "君不见高堂明镜悲白发，朝如青丝暮成雪。",
  "人生得意须尽欢，莫使金樽空对月。",
  "天生我材必有用，千金散尽还复来。",
  "烹羊宰牛且为乐，会须一饮三百杯。",
  "岑夫子，丹丘生，将进酒，杯莫停。",
  "与君歌一曲，请君为我倾耳听。",
  "钟鼓馔玉不足贵，但愿长醉不复醒。",
  "古来圣贤皆寂寞，惟有饮者留其名。",
  "陈王昔时宴平乐，斗酒十千恣欢谑。",
  "主人何为言少钱，径须沽取对君酌。",
  "五花马，千金裘，呼儿将出换美酒，",
  "与尔同销万古愁。",
]);
</script>

<style scoped>
.poem-container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #f5f5dc 0%, #e6d7b9 100%);
  padding: 20px;
}

.poem-card {
  background: rgba(255, 255, 250, 0.95);
  border-radius: 12px;
  padding: 40px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  border: 1px solid rgba(255, 215, 0, 0.3);
  max-width: 800px;
  position: relative;
  overflow: hidden;
}

.poem-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: radial-gradient(
      circle at 20% 50%,
      rgba(255, 0, 0, 0.05) 0%,
      transparent 50%
    ),
    radial-gradient(
      circle at 80% 20%,
      rgba(255, 215, 0, 0.05) 0%,
      transparent 50%
    ),
    radial-gradient(circle at 40% 80%, rgba(0, 0, 0, 0.03) 0%, transparent 50%);
  pointer-events: none;
}

.poem-header {
  text-align: center;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 2px solid rgba(255, 0, 0, 0.2);
}

.poem-title {
  font-size: 2.5rem;
  font-weight: bold;
  color: #8b0000;
  margin: 0 0 10px 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  font-family: "SimSun", serif;
}

.poem-meta {
  display: flex;
  justify-content: center;
  gap: 20px;
  color: #666;
  font-size: 1rem;
}

.poem-content {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.verse {
  font-size: 1.2rem;
  line-height: 1.8;
  color: #333;
  text-align: center;
  font-family: "SimSun", serif;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-out;
}

.verse.animated {
  animation: fadeInUp 0.8s ease-out forwards;
}

.verse.animated.delay-0 {
  animation-delay: 0.1s;
}
.verse.animated.delay-1 {
  animation-delay: 0.2s;
}
.verse.animated.delay-2 {
  animation-delay: 0.3s;
}
.verse.animated.delay-3 {
  animation-delay: 0.4s;
}
.verse.animated.delay-4 {
  animation-delay: 0.5s;
}
.verse.animated.delay-5 {
  animation-delay: 0.6s;
}
.verse.animated.delay-6 {
  animation-delay: 0.7s;
}
.verse.animated.delay-7 {
  animation-delay: 0.8s;
}
.verse.animated.delay-8 {
  animation-delay: 0.9s;
}
.verse.animated.delay-9 {
  animation-delay: 1s;
}
.verse.animated.delay-10 {
  animation-delay: 1.1s;
}
.verse.animated.delay-11 {
  animation-delay: 1.2s;
}
.verse.animated.delay-12 {
  animation-delay: 1.3s;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 背景纹理动画 */
.poem-container {
  position: relative;
  overflow: hidden;
}

.poem-container::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 10px,
      rgba(0, 0, 0, 0.01) 10px,
      rgba(0, 0, 0, 0.01) 20px
    ),
    repeating-linear-gradient(
      -45deg,
      transparent,
      transparent 10px,
      rgba(0, 0, 0, 0.01) 10px,
      rgba(0, 0, 0, 0.01) 20px
    );
  animation: backgroundFlow 20s linear infinite;
  pointer-events: none;
}

@keyframes backgroundFlow {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(50px, 50px);
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .poem-card {
    padding: 20px;
    margin: 10px;
  }

  .poem-title {
    font-size: 2rem;
  }

  .verse {
    font-size: 1rem;
    line-height: 1.6;
  }

  .poem-meta {
    flex-direction: column;
    gap: 5px;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .poem-title {
    font-size: 1.5rem;
  }

  .verse {
    font-size: 0.9rem;
    line-height: 1.5;
  }
}
</style>
