<template>
    <div class="timer">
      <div>
        <div class="timer__image timer__image-top">
          <img class="timer__svg" src="../assets/plant.png" />
        </div>
      </div>
      <div>
        <div class="container">
          <div class="timer__wrapper">
            <h3 class="timer__title">До торжества осталось:</h3>
            <div class="timer__wrap">
              <div class="timer__days">
                <h3 class="timer__number">{{ days }}</h3>
                <h3 class="timer__text">дней</h3>
              </div>
              <div class="timer__line"></div>
              <div class="timer__hours">
                <h3 class="timer__number">{{ hours }}</h3>
                <h3 class="timer__text">часов</h3>
              </div>
              <div class="timer__line"></div>
              <div class="timer__minutes">
                <h3 class="timer__number">{{ minutes }}</h3>
                <h3 class="timer__text">минут</h3>
              </div>
              <div class="timer__line"></div>
              <div class="timer__seconds">
                <h3 class="timer__number">{{ seconds }}</h3>
                <h3 class="timer__text">секунд</h3>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div class="timer__image timer__image-bottom">
          <img class="timer__svg" src="../assets/plant.png" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        targetDate: new Date("2025-08-16T00:00:00"),
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0
      };
    },
    methods: {
      updateTime() {
        const now = new Date();
        const timeLeft = this.targetDate - now;
  
        if (timeLeft > 0) {
          this.days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
          this.hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
          this.minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
          this.seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);
        }
      }
    },
    mounted() {
      this.updateTime();
      setInterval(this.updateTime, 1000);
    }
  };
  </script>

<style>

</style>