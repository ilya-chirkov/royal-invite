<template>
  <div class="contacts">
    <div class="container">
      <div class="contacts__wrapper">
        <div>
          <h3 class="contacts__title">Contacts</h3>
        </div>
        <div>
          <p class="contacts__text">
            В день торжества мы будем очень заняты, поэтому любой вопрос можно
            адресовать координатору. Если у вас есть необычный сюрприз или
            подарок, сообщите об этом ей заранее , чтобы воплотить задуманное в
            жизнь.
          </p>
        </div>
        <div>
          <p class="contacts__text contacts__text-name">Диана:</p>
        </div>
        <div>
          <div class="contacts__wrap">
            <div>
              <div class="contacts__linkwrap">
                <a class="contacts__link" href="tel:+37529000000"
                  >+375290000000</a
                >
              </div>
            </div>
            <div>
              <div class="contacts__linkwrap">
                <a class="contacts__link" href="https://www.instagram.com/"
                  >Instagram</a
                >
              </div>
            </div>
            <div>
              <div class="contacts__linkwrap">
                <a class="contacts__link" href="https://web.telegram.org/a/"
                  >Telegram</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>


.contacts {
    margin: 0 auto 150px;
  }
  .contacts .container {
    margin: 0 auto;
    max-width: 1280px;
    padding: 0 40px;
    position: relative;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .contacts .container {
      padding: 0 60px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .contacts .container {
      padding: 0 35px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .contacts .container {
      padding: 0 20px;
    }
  }
  .contacts__wrapper {
    margin: 0 auto;
    max-width: 800px;
    width: 100%;
  }
  @media (min-width: 769px) and (max-width: 1024px) {
    .contacts__wrapper {
      max-width: 730px;
    }
  }
  @media (min-width: 435px) and (max-width: 770px) {
    .contacts__wrapper {
      max-width: 600px;
    }
  }
  @media (min-width: 320px) and (max-width: 434px) {
    .contacts__wrapper {
      max-width: 320px;
    }
  }
  .contacts__title {
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
    .contacts__title {
      font-size: 36px;
      line-height: 44px;
      margin-bottom: 50px;
      max-width: 200px;
    }
  }
  .contacts__text {
    color: #665f55;
    font-family: Open Sans, serif;
    font-size: 16px;
    font-weight: 300;
    line-height: 22px;
    margin-bottom: 40px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 699px) {
    .contacts__text {
      font-size: 14px;
      line-height: 20px;
    }
  }
  .contacts__text-name {
    font-size: 20px;
    font-weight: 400;
    line-height: 26px;
    margin-bottom: 20px;
  }
  @media (min-width: 320px) and (max-width: 699px) {
    .contacts__text-name {
      font-size: 18px;
      line-height: 26px;
      margin-bottom: 10px;
    }
  }
  .contacts__link {
    background-color: #665f55;
    border: none;
    color: #fff;
    display: block;
    font-family: Open Sans, sans-serif;
    font-size: 18px;
    font-weight: 400;
    line-height: 25px;
    margin: 0 auto 50px;
    padding: 10px;
    text-align: center;
    text-decoration: none;
    width: 220px;
  }
  @media (min-width: 700px) and (max-width: 770px) {
    .contacts__link {
      font-size: 16px;
      line-height: 23px;
      max-width: 170px;
    }
  }
  @media (min-width: 320px) and (max-width: 699px) {
    .contacts__link {
      font-size: 14px;
      line-height: 16px;
      margin-bottom: 30px;
      width: 200px;
    }
  }
  .contacts__link:focus,
  .contacts__link:hover {
    box-shadow: 0 0 10px #665f55;
  }
  .contacts__link:focus {
    background-color: #665f55;
  }
  @media (min-width: 700px) and (max-width: 770px) {
    .contacts__wrap {
      align-items: center;
      display: flex;
      justify-content: space-between;
      margin: 0 auto;
      width: 100%;
    }
  }
  @media (min-width: 771px) {
    .contacts__wrap {
      align-items: center;
      display: flex;
      justify-content: space-between;
      margin: 0 auto;
      width: 100%;
    }
  }
</style>