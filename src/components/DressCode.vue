<template>
  <div class="dresscode">
    <div class="container">
      <div class="dresscode__rapper">
        <h3 class="dresscode__title">Дресс-код</h3>
        <p class="dresscode__text">
          Нам будет особенно приятно видеть вас в нарядах цветовой гаммы&nbsp;
          нашей свадьбы:
        </p>
        <div v-for="(row, rowIndex) in groupedColors" :key="rowIndex" class="dresscode__wrapper">
          <div 
            v-for="(color, index) in row" 
            :key="index" 
            class="dresscode__color"
            :style="{ backgroundColor: color }"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colors: [
  "#005f56", "#003f3a", "#00796b", "#009688", "#00bfa5", // Градиенты изумрудного
  "#000000", "#222222", "#444444", "#666666", "#888888", // Чёрные и серые оттенки
  "#faeacb", "#f5deb3", "#eed9c4", "#e6cdaa", "#dab896", // Шампань и его градиенты
  "#ffffff", "#f8f8f8", "#f0f0f0", "#e8e8e8", "#dcdcdc"  // Белые и светлые оттенки
]
    };
  },
  computed: {
    groupedColors() {
      return Array.from({ length: 4 }, (_, i) => this.colors.slice(i * 5, i * 5 + 5));
    }
  }
};
</script>

<style>
.dresscode {
  margin: 0 auto 150px;
}

@media (max-width: 767px) {
  .dresscode {
    margin-bottom: 150px;
  }
}

.dresscode .container {
  margin: 0 auto;
  max-width: 1280px;
  padding: 0 clamp(20px, 5vw, 60px);
  position: relative;
}

.dresscode__wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 5px;
  margin: 0 auto 5px;
  max-width: min(600px, 90%);
  position: relative;
  width: 100%;
}

.dresscode__title {
  border-bottom: 1px solid #665f55;
  color: #665f55;
  font-family: KyivType Sans, sans-serif;
  font-size: clamp(36px, 4vw, 46px);
  font-weight: 200;
  line-height: clamp(44px, 5vw, 56px);
  margin: 0 auto 65px;
  max-width: 300px;
  position: relative;
  text-align: center;
  width: 100%;
}

@media (max-width: 767px) {
  .dresscode__title {
    margin-bottom: 50px;
    max-width: 250px;
  }
}

.dresscode__text {
  color: #665f55;
  font-family: Open Sans, serif;
  font-size: clamp(14px, 2vw, 16px);
  font-weight: 300;
  line-height: clamp(20px, 2.5vw, 22px);
  margin: 0 auto 20px;
  padding: 0 clamp(20px, 5vw, 40px);
  text-align: center;
  max-width: min(730px, 90%);
}

.dresscode__text-people {
  font-size: clamp(22px, 3vw, 24px);
  line-height: clamp(26px, 3.5vw, 28px);
  margin-bottom: 30px;
}

.dresscode__wrap {
  margin: 0 auto 20px;
}

.dresscode__jpg {
  height: 100%;
  object-fit: cover;
  width: 100%;
}

.dresscode__color {
  height: clamp(55px, 10vw, 120px);
  width: clamp(55px, 10vw, 120px);
  border-radius: 50%;
}

</style>