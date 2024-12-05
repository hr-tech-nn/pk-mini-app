<template>
  <div class="flex flex-col">
    <div class="carousel-block">
      <NCarousel
        autoplay
        effect="card"
        prev-slide-style="transform: translateX(-150%) translateZ(-800px);"
        next-slide-style="transform: translateX(50%) translateZ(-800px);"
        style="height: 248px"
        :show-dots="false"
      >
        <NCarouselItem :style="{ width: '40%' }">
          <img
            class="carousel-img"
            src="/carousel_img_1.jpg"
          >
        </NCarouselItem>
        <NCarouselItem :style="{ width: '40%' }">
          <img
            class="carousel-img"
            src="/carousel_img_2.jpg"
          >
        </NCarouselItem>
        <NCarouselItem :style="{ width: '40%' }">
          <img
            alt=""
            class="carousel-img"
            src="/carousel_img_3.jpg"
          >
        </NCarouselItem>
        <NCarouselItem :style="{ width: '40%' }">
          <div class="carousel-card relative">
            <img
              alt=""
              class="carousel-img"
              src="/carousel_img_3.jpg"
            >
            <div class="card-text absolute top-0 right-0">SMART</div>
          </div>
        </NCarouselItem>
      </NCarousel>
    </div>

    <div :class="{ 'fixed': isFixed }" class="top-buttons flex justify-around p-4 bg-white z-10">
      <button
        v-for="(button, index) in buttons"
        :key="index"
        :class="[
          'rounded-full border-2 p-2 transition-colors',
          activeButton === index ? 'bg-red-500 text-white' : 'border-red-500 text-black'
        ]"
        @click="setActiveButton(index)"
      >
        {{ button }}
      </button>
    </div>

    <div class="courses-cards flex flex-col pa-5 gap-5">
      <CursPreview v-for="n in 6" :key="n" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const buttons = ['Мои курсы', 'Архив', 'Опросы', 'Обр. связь'];
const activeButton = ref(0);
const isFixed = ref(false);

const setActiveButton = (index: number) => {
  activeButton.value = index;
};

const handleScroll = () => {
  isFixed.value = window.scrollY > 150; // Настройте порог по мере необходимости
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.carousel-img {
  margin: 0 auto;
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.carousel-block{
  margin-top: 60px;
}
.card-text{
  position: absolute;
  top: 192px;
  bottom: 10; /* Позиционируем текст внизу */
  left: 0; /* Устанавливаем левую границу */
  right: 0; /* Устанавливаем правую границу */
  text-align: center; /* Центрируем текст */
  background-color: rgba(0, 0, 0, 0.5); /* Полупрозрачный фон для лучшей читаемости (опционально) */
  color: white; /* Цвет текста (опционально) */
  padding: 8px; /* Отступы (опционально) */
}

.top-buttons {
  position: relative; /* Положение по умолчанию */
}

.fixed {
  position: fixed;
  top: 48px;
  left: 0;
  right: 0;
  box-shadow: none;
}
</style>