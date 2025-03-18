<template>
  <div>
    <div class="main">
      <div class="container">
        <div class="main__wrapper">
          <h1 class="main__letter fade-in scale-up">Д</h1>
          <div class="main__image float">
            <img class="main__jpg" src="../assets/plant.png" alt="couple" />
          </div>
          <h1 class="main__letter fade-in scale-up"> И</h1>
        </div>
        <div class="main__wrap">
          <p class="main__number fade-in">16</p>
          <p class="main__number fade-in">08</p>
          <p class="main__number fade-in">2025</p>
        </div>
        <p class="main__text fade-in">
          Этот день будет для нас особенным, и мы хотим провести его в кругу близких и друзей.
        </p>
        <div class="main__textwrap fade-in">
          <h1 class="main__title scale-up">Диана</h1>
          <h1 class="main__title main__title-middle">&</h1>
          <h1 class="main__title scale-up">Илья</h1>
        </div>
        <p class="main__text main__text-bottom fade-in">
          Ждём Вас!
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:'MainSection'
};
</script>

<style scoped>

.wrapper {
    background-color: #fff;
  }
  .wrapper-dark {
    background-color: #323232;
    color: #fff;
  }
  .main {
    margin-bottom: 50px;
    padding: 70px 0 120px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .main {
      padding: 25px 0 150px;
    }
  }
  .main .container {
    border: 2px groove #aa835c;
    margin: 0 auto;
    max-width: 600px;
    padding: 40px;
    position: relative;
    width: 100%;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .main .container {
      max-width: 500px;
    }
  }
  @media (min-width: 501px) and (max-width: 768px) {
    .main .container {
      max-width: 440px;
    }
  }
  @media (min-width: 400px) and (max-width: 500px) {
    .main .container {
      max-width: 360px;
    }
  }
  @media (min-width: 320px) and (max-width: 399px) {
    .main .container {
      max-width: 300px;
    }
  }
  .main__wrapper {
    align-items: center;
    display: flex;
    justify-content: space-between;
    margin: 0 auto 60px;
    max-width: 280px;
    width: 100%;
  }
  .main__image {
    height: 110px;
    margin: 0 auto;
    position: relative;
    width: 100px;
  }
  @media (min-width: 600px) and (max-width: 768px) {
    .main__image {
      height: 110px;
      width: 100px;
    }
  }
  @media (min-width: 430px) and (max-width: 599px) {
    .main__image {
      height: 90px;
      width: 85px;
    }
  }
  @media (min-width: 320px) and (max-width: 429px) {
    .main__image {
      height: 90px;
      width: 85px;
    }
  }
  .main__jpg {
    height: 100%;
    left: 0;
    object-fit: cover;
    position: absolute;
    top: 0;
    width: 100%;
  }
  .main__letter {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 88px;
    font-weight: 200;
    line-height: 106px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .main__letter {
      font-size: 72px;
      line-height: 94px;
    }
  }
  .main__wrap {
    margin-bottom: 60px;
  }
  .main__number {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 56px;
    font-weight: 200;
    letter-spacing: 10px;
    line-height: 66px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .main__number {
      font-size: 56px;
      line-height: 68px;
    }
  }
  .main__text {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 16px;
    font-weight: 300;
    line-height: 22px;
    margin: 0 auto 35px;
    max-width: 450px;
    text-align: center;
    width: 100%;
    font-weight: 500;
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .main__text {
      font-size: 14px;
      line-height: 20px;
    }
  }
  .main__text-bottom {
    margin-bottom: 0;
  }
  .main__title {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 32px;
    font-weight: 200;
    line-height: 38px;
    text-align: center;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .main__title {
      font-size: 28px;
      line-height: 38px;
    }
  }
  @media (min-width: 600px) and (max-width: 768px) {
    .main__title {
      font-size: 30px;
      line-height: 38px;
    }
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .main__title {
      font-size: 26px;
      line-height: 34px;
    }
  }
  .main__title-middle {
    color: #665f55;
    font-size: 42px;
    font-weight: 200;
    line-height: 48px;
    text-align: center;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .main__title-middle {
      font-size: 42px;
      line-height: 48px;
    }
  }
  @media (min-width: 600px) and (max-width: 768px) {
    .main__title-middle {
      font-size: 42px;
      line-height: 48px;
    }
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .main__title-middle {
      font-size: 38px;
      line-height: 44px;
    }
  }
  .main__textwrap {
    align-items: center;
    column-gap: 15px;
    display: flex;
    justify-content: center;
    letter-spacing: 10px;
    margin: 0 auto 40px;
  }
  @media (min-width: 600px) and (max-width: 768px) {
    .main__textwrap {
      letter-spacing: 5px;
      margin-bottom: 60px;
    }
  }
  @media (min-width: 430px) and (max-width: 599px) {
    .main__textwrap {
      column-gap: 10px;
      letter-spacing: 0;
    }
  }
  @media (min-width: 320px) and (max-width: 429px) {
    .main__textwrap {
      column-gap: 8px;
      letter-spacing: 0;
    }
  }
  /* Анимация появления */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes scaleUp {
  from {
    transform: scale(0.8);
  }
  to {
    transform: scale(1);
  }
}

@keyframes float {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
  100% {
    transform: translateY(0);
  }
}

.fade-in {
  animation: fadeIn 1s ease-in-out;
}

.scale-up {
  animation: scaleUp 0.8s ease-in-out;
}

.float {
  animation: float 3s ease-in-out infinite;
}
</style>