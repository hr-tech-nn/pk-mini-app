<script setup lang="ts">

</script>

<template>
  <div class="preview-card h-150px flex flex-row justify-center items-center w-full">
    <div class="pa-2 flex flex-row justify-center items-center gap-2">
      <div class="image-container">
        <img :src="'/Card image 1.png'" alt="Card image" class="card-image" />
      </div>
      <div class=" w-full flex flex-col justify-center">
        <h2 class="card-title">5 шагов продаж</h2>
        <p class="card-subtitle">Обучает эффективным техникам и стратегиям продаж, помогая достигать высоких результатов в любой сфере бизнеса.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.preview-card {
  border-radius: 16px;
  border: 1px solid red;
  display: flex;
}

.image-container {
  width: 96px; /* Ширина изображения */
  height: 136px; /* Высота изображения */
}

.card-image {

  border-radius: 8px; /* Закругление углов изображения */
}

.card-title {
  font-size: 1.5em;
  margin: 0; /* Убираем отступы */
  display: -webkit-box; /* Используем flexbox для многострочного текста */
    -webkit-box-orient: vertical; /* Устанавливаем направление оси для flexbox */
    -webkit-line-clamp: 2; /* Ограничиваем количество строк до 3 */
    overflow: hidden; /* Скрываем переполнение */
    text-overflow: ellipsis; /* Добавляем многоточие в конце */
    max-height: 4.5em; /* Максимальная высота для 3 строк (примерно 1.5em на строку) */
    line-height: 1.5em; /* Высота строки */

}

.card-subtitle {
  color: #666; /* Цвет подзаголовка */
  margin-top: 8px; /* Добавляем небольшой отступ сверху для подзаголовка */
    display: -webkit-box; /* Используем flexbox для многострочного текста */
    -webkit-box-orient: vertical; /* Устанавливаем направление оси для flexbox */
    -webkit-line-clamp: 3; /* Ограничиваем количество строк до 3 */
    overflow: hidden; /* Скрываем переполнение */
    text-overflow: ellipsis; /* Добавляем многоточие в конце */
    max-height: 4.5em; /* Максимальная высота для 3 строк (примерно 1.5em на строку) */
    line-height: 1.5em; /* Высота строки */
}
</style>