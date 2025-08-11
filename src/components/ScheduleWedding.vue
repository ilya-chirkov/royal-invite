<template>
  <div class="timing">
    <div class="container">
      <div class="timing__wrap">
        <div>
          <h2 class="timing__title">Время</h2>
        </div>
        <div class="timing__content">
          <div v-for="(event, index) in events" :key="index" class="timing__wrapper">
            <div class="timing__img">
              <div>
                <img
                  loading="lazy"
                  class="timing__png"
                  :src="require(`@/assets/${event.image}`)"
                  :alt="event.altText"
                />
              </div>
            </div>
            <div class="timing__textwrap">
              <div>
                <div class="timing__textwraptop">
                  <p class="timing__subtitle">{{ event.time }}</p>
                  <p class="timing__text">{{ event.title }}</p>
                </div>
              </div>
              <div>
                <div class="timing__textwrapbottom">
                  <p class="timing__text timing__text-bottom">
                    {{ event.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          time: "14:40",
          title: "Трансфер",
          description:
            "При необходимости трансфера вас будет ожидать микроавтобус, который отвезет вас прямиком на наше мероприятие! (Время пока что приблизительное)",
          image: "t1.png",
          altText: "couple",
        },
        {
          time: "15:20",
          title: "Фуршет",
          description:
            "Расслабьтесь и познакомьтесь с другими гостями перед торжеством",
          image: "t3.png",
          altText: "couple",
        },
        {
          time: "16:00",
          title: "Выездная церемония",
          description: "Разделите с нами трогательный момент создания семьи",
          image: "t2.png",
          altText: "couple",
        },
        {
          time: "17:00",
          title: "Праздничный банкет",
          description:
            "Танцуйте, веселитесь и выпивайте за нашу любовь!",
          image: "t4.png",
          altText: "couple",
        },
        {
          time: "23:30",
          title: "Окончание банкета",
          description:
            "Вечер подойдет к концу, а с вами останутся приятные воспоминания!",
          image: "t6.png",
          altText: "couple",
        },
      ],
    };
  },
};
</script>



<style scoped>
  .timing {
    margin-bottom: 110px;
    margin-top: -70px;
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