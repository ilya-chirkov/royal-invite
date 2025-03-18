<template>
  <div class="details">
    <div>
      <div class="details__image details__image-top">
        <img class="details__svg" src="../assets/plant.png" />
      </div>
    </div>
    <div class="container">
      <div class="details__wrap">
        <div>
          <h2 class="details__title">Детали</h2>
        </div>
        <div>
          <div class="details__content">
            <div class="details__line"></div>
            <div class="details__wrapper">
              <div class="details__imgwrap">
                <img class="details__svg" src="../assets/Rectangle159.svg" alt="rect" />
              </div>
              <div class="details__textwrap">
                <p class="details__text">
                  Если вы предпочитаете подарить денежный вклад, мы будем очень
                  благодарны за вашу щедрость и понимание. Это поможет нам
                  осуществить наши мечты и планы на будущее.
                </p>
              </div>
            </div>
            <div class="details__wrapper">
              <div class="details__imgwrap">
                <img class="details__svg" src="../assets/Rectangle159.svg" alt="rect" />
              </div>
              <div class="details__textwrap">
                <p class="details__text">
                  Вместо традиционных цветов, мы хотели бы попросить вас
                  принести с собой бутылочку вашего любимого алкогольного
                  напитка.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="details__image details__image-bottom">
        <img class="details__svg" src="../assets/plant.png" />
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>


.details {
    margin: 0 auto 175px;
    position: relative;
    width: 100%;
  }
  .details .container {
    margin: 0 auto;
    max-width: 1280px;
    max-width: 800px;
    padding: 0 40px;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .details .container {
      padding: 0 60px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .details .container {
      padding: 0 35px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .details .container {
      padding: 0 20px;
    }
  }
  .details__wrap {
    margin: 0 auto;
    max-width: 800px;
    width: 100%;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .details__wrap {
      max-width: 730px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .details__wrap {
      max-width: 600px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .details__wrap {
      max-width: 320px;
    }
  }
  .details__title {
    border-bottom: 1px solid #665f55;
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 46px;
    font-weight: 200;
    line-height: 56px;
    margin: 0 auto 80px;
    max-width: 180px;
    text-align: center;
    width: 100%;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .details__title {
      font-size: 36px;
      line-height: 44px;
      margin-bottom: 50px;
      max-width: 150px;
    }
  }
  .details__text {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 16px;
    font-weight: 300;
    line-height: 22px;
    text-align: justify;
    text-indent: 20px;
  }
  @media (min-width: 320px) and (max-width: 599px) {
    .details__text {
      font-size: 14px;
      line-height: 20px;
    }
  }
  .details__imgwrap {
    height: 15px;
    width: 15px;
    z-index: 3;
  }
  .details__image,
  .details__imgwrap {
    align-items: center;
    display: flex;
    justify-content: center;
  }
  .details__image {
    height: 300px;
    width: 300px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .details__image {
      height: 150px;
      width: 150px;
    }
  }
  @media (min-width: 768px) and (max-width: 1023px) {
    .details__image {
      height: 200px;
      width: 200px;
    }
  }
  .details__image-top {
    opacity: 0.6;
    position: absolute;
    right: -25px;
    top: -170px;
    transform: scaleX(-1) rotate(125deg);
  }
  .details__image-bottom {
    bottom: -300px;
    left: -25px;
    opacity: 0.6;
    position: absolute;
    transform: scaleX(-1) rotate(-50deg);
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .details__image-bottom {
      bottom: -200px;
    }
  }
  @media (min-width: 768px) and (max-width: 1023px) {
    .details__image-bottom {
      bottom: -235px;
    }
  }
  .details__svg {
    height: 100%;
    object-fit: contain;
  }
  .details__wrapper {
    align-items: center;
    column-gap: 60px;
    display: flex;
    justify-content: flex-start;
    margin-bottom: 50px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .details__wrapper {
      column-gap: 20px;
    }
  }
  .details__content {
    position: relative;
  }
  .details__line {
    border-left: 1px solid #665f55;
    height: 100%;
    left: 7px;
    max-height: 200px;
    position: absolute;
    top: 0;
    z-index: -100;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .details__line {
      max-height: 350px;
    }
  }
</style>