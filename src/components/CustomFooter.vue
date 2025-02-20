<template>
  <footer>
    <div class="footer">
      <div>
        <div class="container">
          <h3 class="footer__title">До встречи на торжестве!</h3>
          <div class="footer__image">
            <img class="footer__png" src="../assets/wish.jpeg" />
          </div>
          <div class="footer__textwrap">
            <div class="footer__wrapdata">
              <p class="footer__data footer__data-top">16|08</p>
              <p class="footer__data footer__data-bottom">2025</p>
            </div>
            <div class="footer__namewrap">
              <p class="footer__text">Диана</p>
              <p class="footer__and">&amp;</p>
              <p class="footer__text">Илья</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style>


.footer {
    padding: 10px 0 50px;
  }
  .footer__title {
    color: #665f55;
    font-family: Open Sans, sans-serif;
    font-size: 36px;
    font-weight: 300;
    line-height: 46px;
    margin-bottom: 20px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__title {
      font-size: 24px;
      line-height: 38px;
    }
  }
  .footer__image {
    height: 800px;
    margin: 0 auto 70px;
    width: 530px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__image {
      height: 450px;
      margin-bottom: 50px;
      width: 300px;
    }
  }
  .footer__png {
    height: 100%;
    object-fit: cover;
    width: 100%;
  }
  .footer__textwrap {
    align-items: center;
    display: flex;
    justify-content: space-around;
    margin: 0 auto;
    max-width: 530px;
    width: 100%;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__textwrap {
      justify-content: space-between;
      max-width: 300px;
    }
  }
  .footer__data {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 36px;
    font-weight: 200;
    letter-spacing: 3px;
    line-height: 46px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__data {
      font-size: 28px;
      line-height: 32px;
    }
  }
  .footer__data-top {
    letter-spacing: 5px;
  }
  .footer__data-bottom {
    letter-spacing: 10px;
  }
  .footer__text {
    color: #665f55;
    font-family: KyivType Sans;
    font-size: 32px;
    font-weight: 200;
    line-height: 44px;
    text-align: center;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__text {
      font-size: 28px;
      line-height: 32px;
    }
  }
  .footer__namewrap {
    position: relative;
  }
  .footer__and {
    color: #665f55;
    font-family: Open Sans, sans-serif;
    font-size: 110px;
    font-weight: 300;
    left: 50px;
    line-height: 150px;
    opacity: 0.15;
    position: absolute;
    text-align: center;
    top: -32px;
  }
  @media (min-width: 320px) and (max-width: 767px) {
    .footer__and {
      font-size: 90px;
      left: 50px;
      top: -42px;
    }
  }
</style>