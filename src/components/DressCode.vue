<template>
  <div class="dresscode">
    <div class="container">
      <div class="dresscode__rapper">
        <h3 class="dresscode__title">Dress-code</h3>
        <p class="dresscode__text">
          Нам будет особенно приятно видеть вас в нарядах цветовой гаммы нашей
          свадьбы:
        </p>

        <!-- Блок с цветами -->
        <div class="dresscode__wrapper">
          <div
            v-for="(color, index) in dressColors"
            :key="index"
            class="dresscode__color"
            :style="{ backgroundColor: color }"
          ></div>
        </div>

        <!-- Слайдер изображений -->
        <swiper
          :slidesPerView="1"
          :spaceBetween="20"
          :loop="true"
          :autoplay="{ delay: 3000 }"
          :effect="'fade'"
          class="mySwiper"
        >
          <swiper-slide v-for="(image, index) in images" :key="index">
            <div class="dresscode__wrap">
              <img
                class="dresscode__jpg"
                :src="image"
                alt="Dress-code пример"
              />
            </div>
          </swiper-slide>

          <!-- Индикаторы слайдов -->
          <template v-slot:pagination>
            <div class="slick-dots">
              <button
                v-for="(image, index) in images"
                :key="index"
                @click="currentIndex = index"
                :class="{ 'slick-active': index === currentIndex }"
              >
                {{ index + 1 }}
              </button>
            </div>
          </template>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>
// Импортируем Swiper и его стили
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      dressColors: ["#0D4033", "#000000", "#F5ECD7", "#8C7A6B", "#D4C9C1"],
      images: [
        new URL("@/assets/dr1.jpg", import.meta.url).href,
        new URL("@/assets/dr1.jpg", import.meta.url).href,
        new URL("@/assets/dr3.jpg", import.meta.url).href,
        new URL("@/assets/dr3.jpg", import.meta.url).href,
      ],
      currentIndex: 0,
    };
  },
};
</script>

<style scoped>
.dresscode {
  margin: 0 auto 150px;
}
.dresscode .container {
  max-width: 1280px;
  padding: 0 40px;
  margin: 0 auto;
}
.dresscode__rapper {
  max-width: 800px;
  margin: 0 auto;
}
.dresscode__title {
  text-align: center;
  font-size: 46px;
  border-bottom: 1px solid #665f55;
}
.dresscode__text {
  text-align: center;
  font-size: 16px;
}
.dresscode__wrapper {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin: 20px auto;
}
.dresscode__color {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

.slick-dots {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 10px;
}
.slick-dots button {
  width: 15px;
  height: 15px;
  border: none;
  background: #ccc;
  border-radius: 50%;
  cursor: pointer;
}
.slick-dots .slick-active button {
  background: #665f55;
}

/* Стили для изображения */
.dresscode__jpg {
  width: 150px;
  height: auto;
  object-fit: cover;
}
</style>
