<template>
  <div class="location">
    <div>
      <h2 class="location__title">Локация</h2>
    </div>
    <div>
      <div class="works">
        <div class="works__wrap">
          <div class="works__content">
            <h3 class="works__title">Усадьба "Экзотика"</h3>
            <p class="works__text">г.Бобруйск, д. Спорное 29 </p>
          </div>
        </div>
        <div class="works__wrap">
          <img class="works__jpg" src="../assets/loc2.jpg" alt="work" />
        </div>
        <div class="works__wrap works__wrap-none">
          <div class="works__content">
            <h3 class="works__title">Праздничный банкет</h3>
            <p class="works__text">16.30</p>
          </div>
        </div>
        <div class="works__wrap">
          <img class="works__jpg" src="../assets/loс1.jpg" alt="work" />
        </div>
        <div class="works__wrap">
          <div class="works__content">
            <a class="works__link" href="https://yandex.by/maps/-/CHuimQ5g"
              >Посмотреть на карте</a
            >
          </div>
        </div>
        <div class="works__wrap works__wrap-none">
          <img class="works__jpg" src="../assets/loc2.jpg" alt="work" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>

.location {
    margin-bottom: 150px;
  }
  .location__title {
    border-bottom: 1px solid #665f55;
    color: #0c2f0d;
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
    .location__title {
      font-size: 36px;
      line-height: 44px;
      margin-bottom: 50px;
      max-width: 180px;
    }
  }
  .works {
    grid-column-gap: 0;
    grid-row-gap: 0;
    column-gap: 0;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    margin-bottom: 150px;
    row-gap: 0;
  }
  @media (min-width: 768px) and (max-width: 1024px) {
    .works {
      margin-bottom: 78px;
    }
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .works {
      grid-template-columns: 1fr 1fr;
      margin-bottom: 35px;
    }
  }
  .works__wrap {
    position: relative;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .works__wrap-none {
      display: none;
    }
  }
  .works__wrap:before {
    content: "";
    display: block;
    padding-top: 100%;
  }
  .works__jpg {
    height: 100%;
    left: 0;
    object-fit: cover;
    position: absolute;
    top: 0;
    width: 100%;
  }
  .works__title {
    font-family: OpenSans, sans-serif;
    font-size: 22px;
    font-weight: 300;
    line-height: 26px;
    margin-bottom: 30px;
    text-align: center;
    text-transform: uppercase;
  }
  @media (min-width: 768px) and (max-width: 1024px) {
    .works__title {
      font-size: 19px;
      line-height: 22px;
      margin-bottom: 25px;
    }
  }
  @media (min-width: 550px) and (max-width: 767px) {
    .works__title {
      font-size: 16px;
      line-height: 20px;
      margin-bottom: 25px;
    }
  }
  @media (min-width: 440px) and (max-width: 549px) {
    .works__title {
      font-size: 14px;
      line-height: 18px;
      margin-bottom: 20px;
      text-transform: none;
      text-transform: uppercase;
    }
  }
  @media (min-width: 320px) and (max-width: 439px) {
    .works__title {
      font-size: 11px;
      line-height: 15px;
      margin-bottom: 20px;
      text-transform: none;
      text-transform: uppercase;
    }
  }
  .works__link {
    border-bottom: 1px solid #fff;
    color: #fff;
    cursor: pointer;
    font-family: OpenSans, sans-serif;
    font-size: 22px;
    font-weight: 300;
    line-height: 26px;
    margin: 0 auto;
    max-width: 280px;
    text-align: center;
    text-decoration: none;
    text-transform: uppercase;
    width: 100%;
  }
  @media (min-width: 768px) and (max-width: 1024px) {
    .works__link {
      font-size: 19px;
      line-height: 22px;
      max-width: 246px;
    }
  }
  @media (min-width: 550px) and (max-width: 767px) {
    .works__link {
      font-size: 16px;
      line-height: 20px;
      max-width: 210px;
    }
  }
  @media (min-width: 440px) and (max-width: 549px) {
    .works__link {
      font-size: 14px;
      line-height: 18px;
      max-width: 182px;
      text-transform: uppercase;
    }
  }
  @media (min-width: 320px) and (max-width: 439px) {
    .works__link {
      font-size: 11px;
      line-height: 15px;
      max-width: 142px;
      text-transform: uppercase;
    }
  }
  .works__link:hover {
    font-weight: 400;
  }
  .works__link:focus {
    border-bottom: 1px solid #fff;
    color: #fff;
    font-weight: 400;
  }
  .works__text {
    font-family: OpenSans, sans-serif;
    font-size: 18px;
    font-weight: 300;
    line-height: 24px;
  }
  @media (min-width: 768px) and (max-width: 1023px) {
    .works__text {
      font-size: 16px;
      line-height: 22px;
    }
  }
  @media (min-width: 440px) and (max-width: 767px) {
    .works__text {
      font-size: 14px;
      line-height: 18px;
    }
  }
  @media (min-width: 320px) and (max-width: 439px) {
    .works__text {
      font-size: 11px;
      line-height: 15px;
    }
  }
  .works__content {
    background-color: #0000;
    background-color: #665f55;
    color: #fff;
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    left: 0;
    padding: 10px;
    position: absolute;
    text-align: center;
    top: 0;
    width: 100%;
  }
</style>