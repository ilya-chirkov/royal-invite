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

<style scoped>
  .timer {
    margin-bottom: 350px;
    position: relative;
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .timer {
      margin-bottom: 250px;
    }
  }
  .timer .container {
    margin: 0 auto;
    max-width: 1280px;
    padding: 0 40px;
    position: relative;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .timer .container {
      padding: 0 60px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .timer .container {
      padding: 0 35px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .timer .container {
      padding: 0 20px;
    }
  }
  .timer__wrapper {
    margin: 0 auto;
    max-width: 800px;
    width: 100%;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .timer__wrapper {
      max-width: 730px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .timer__wrapper {
      max-width: 600px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .timer__wrapper {
      max-width: 320px;
    }
  }
  .timer__title {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 20px;
    font-weight: 300;
    line-height: 28px;
    margin-bottom: 50px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__title {
      font-size: 18px;
      line-height: 26px;
    }
  }
  .timer__wrap {
    align-items: center;
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    max-width: 440px;
    position: relative;
    width: 100%;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__wrap {
      max-width: 270px;
    }
  }
  .timer__number {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 36px;
    font-weight: 200;
    line-height: 46px;
    position: relative;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__number {
      font-size: 26px;
      line-height: 32px;
    }
  }
  .timer__text {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 16px;
    font-weight: 300;
    line-height: 22px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__text {
      font-size: 12px;
      line-height: 16px;
    }
  }
  .timer__line {
    border-right: 1px solid #665f55;
    height: 85px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__line {
      height: 50px;
    }
  }
  .timer__image {
    align-items: center;
    display: flex;
    height: 300px;
    justify-content: center;
    width: 300px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__image {
      height: 150px;
      width: 150px;
    }
  }
  @media (min-width: 768px) and (max-width: 1023px) {
    .timer__image {
      height: 200px;
      width: 200px;
    }
  }
  .timer__image-top {
    left: -25px;
    opacity: 0.6;
    position: absolute;
    top: -170px;
    transform: rotate(125deg);
  }
  .timer__image-bottom {
    bottom: -300px;
    opacity: 0.6;
    position: absolute;
    right: -25px;
    transform: rotate(-50deg);
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timer__image-bottom {
      bottom: -200px;
    }
  }
  @media (min-width: 768px) and (max-width: 1023px) {
    .timer__image-bottom {
      bottom: -235px;
    }
  }
  .timer__svg {
    height: 100%;
    object-fit: contain;
  }
  .timing {
    margin-bottom: 150px;
  }
  .timing .container {
    margin: 0 auto;
    max-width: 1280px;
    max-width: 800px;
    padding: 0 40px;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .timing .container {
      padding: 0 60px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .timing .container {
      padding: 0 35px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .timing .container {
      padding: 0 20px;
    }
  }
  .timing__wrap {
    margin: 0 auto;
    max-width: 800px;
    width: 100%;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .timing__wrap {
      max-width: 730px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .timing__wrap {
      max-width: 600px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .timing__wrap {
      max-width: 320px;
    }
  }
  .timing__wrapper {
    column-gap: 20px;
    justify-content: space-between;
    margin: 0 auto 80px;
    max-width: 700px;
    width: 100%;
  }
  .timing__img,
  .timing__wrapper {
    align-items: center;
    display: flex;
  }
  .timing__img {
    height: 80px;
    justify-content: center;
    width: 80px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timing__img {
      height: 60px;
      width: 60px;
    }
  }
  .timing__png {
    height: 100%;
    object-fit: contain;
    width: 100%;
  }
  .timing__textwrap,
  .timing__textwraptop {
    max-width: 550px;
    width: 100%;
  }
  .timing__textwraptop {
    align-items: center;
    border-bottom: 1px solid #665f55;
    column-gap: 50px;
    display: flex;
    justify-content: start;
    margin-bottom: 10px;
  }
  @media (min-width: 360px) and (max-width: 767px) {
    .timing__textwraptop {
      column-gap: 20px;
    }
  }
  @media (min-width: 320px) and (max-width: 359px) {
    .timing__textwraptop {
      column-gap: 10px;
    }
  }
  .timing__title {
    border-bottom: 1px solid #665f55;
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 46px;
    font-weight: 200;
    line-height: 56px;
    margin: 0 auto 65px;
    max-width: 225px;
    position: relative;
    text-align: center;
    width: 100%;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .timing__title {
      font-size: 36px;
      line-height: 44px;
      margin-bottom: 50px;
      max-width: 180px;
    }
  }
  .timing__subtitle {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 22px;
    font-weight: 400;
    line-height: 30px;
  }
  @media (min-width: 360px) and (max-width: 767px) {
    .timing__subtitle {
      font-size: 20px;
      line-height: 27px;
    }
  }
  @media (min-width: 320px) and (max-width: 359px) {
    .timing__subtitle {
      font-size: 18px;
      line-height: 24px;
    }
  }
  .timing__text {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 18px;
    font-weight: 300;
    line-height: 25px;
    text-align: justify;
  }
  @media (min-width: 430px) and (max-width: 767px) {
    .timing__text {
      font-size: 16px;
      line-height: 23px;
    }
  }
  @media (min-width: 320px) and (max-width: 429px) {
    .timing__text {
      font-size: 14px;
      line-height: 20px;
    }
  }
  @media (min-width: 430px) and (max-width: 767px) {
    .timing__text-bottom {
      font-size: 14px;
      line-height: 20px;
    }
  }
  @media (min-width: 320px) and (max-width: 429px) {
    .timing__text-bottom {
      font-size: 13px;
      line-height: 18px;
    }
  }
</style>