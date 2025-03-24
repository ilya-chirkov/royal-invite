<template>
  <div class="form">
    <div class="container">
      <div class="form__wrapper">
        <div>
          <h3 class="form__title">Анкета</h3>
        </div>
        <div>
          <div class="form__textwrap">
            <p class="form__text">Просьба заполнить анкету до 01 июля</p>
          </div>
        </div>
        <div>
          <form
            @submit.prevent="submitForm"
            class="form__wrap"
            id="telegramForm"
          >
            <div class="form__name">
              <p class="form__text form__text-subtitle">Ваше Имя и Фамилия:</p>
              <input
                required="true"
                class="form__input"
                type="text"
                name="user_name"
                id="user-name-input"
                v-model="formData.userName"
                placeholder="Введите свое Имя и Фамилию"
                autocomplete="off"
                value=""
              />
              <!-- <p class="form__text form__text-mini">
                Если вы будете в компании своего спутника/спутницы, просим
                дополнительно внести его/ее данные в графу.
              </p> -->
            </div>
            <div class="form__yes">
              <p class="form__text form__text-subtitle">
                Планируете ли вы присутствовать на свадьбе?
              </p>
              <div class="checkboxes__row">
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="yes"
                    ><input
                      v-model="formData.attending"
                      type="radio"
                      id="yes"
                      name="attending"
                      value="Да"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Да, буду на свадьбе</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="no"
                    ><input
                      v-model="formData.attending"
                      type="radio"
                      id="no"
                      name="attending"
                      value="Нет"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">
                      Нет, не смогу быть на свадьбе
                    </p></label
                  >
                </div>
              </div>
            </div>
            <div class="form__yes">
              <p class="form__text form__text-subtitle">
                Необходим ли трансфер из Бобруйска до усадьбы?
              </p>
              <div class="checkboxes__row">
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="transferYes"
                    ><input
                      v-model="formData.transfer"
                      type="radio"
                      id="transferYes"
                      name="transfer"
                      value="Да"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Да</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="transferNo"
                    ><input
                      v-model="formData.transfer"
                      type="radio"
                      id="transferNo"
                      name="transfer"
                      value="Нет"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Нет</p></label
                  >
                </div>
              </div>
            </div>
            <div class="form__yes form__yes-bottom">
              <p class="form__text form__text-subtitle">
                Какой алкоголь предпочитаете?
              </p>
              <div class="checkboxes__row">
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice1"
                    ><input
                      v-model="formData.alcohol.vine"
                      type="checkbox"
                      id="alcChoice1"
                      name="alcohol"
                      value="Вино"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">
                      Алкоголь средней крепости
                    </p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice5"
                    ><input
                      v-model="formData.alcohol.vodka"
                      type="checkbox"
                      id="alcChoice5"
                      name="alcohol"
                      value="Водка"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Крепкие напитки</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice6"
                    ><input
                      v-model="formData.alcohol.NotDrink"
                      type="checkbox"
                      id="alcChoice6"
                      name="alcohol"
                      value="Безалкогольные напитки"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Только безалкогольные напитки (не пью)</p></label
                  >
                </div>
              </div>
            </div>
            <div class="form__wrapbtn">
              <button class="form__btn" type="submit">Отправить</button>
            </div>
            <div v-if="isModalOpen" class="modal-overlay" @click="closeModal">
              <transition name="fade">
                <div class="modal" @click.stop>
                  <div class="modal__header">
                    <span class="modal__icon">✅</span>
                    <h2>Успешно отправлено!</h2>
                  </div>
                  <p class="modal__text">Спасибо за Ваш ответ!</p>
                  <button class="modal__button" @click="closeModal">Ок</button>
                </div>
              </transition>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";

const isModalOpen = ref(false);
const userNumber = ref(0);

const formData = ref({
  userName: "",
  attending: "",
  transfer: "",
  alcohol: {
    vine: false,
    vodka: false,
    NotDrink: false,
  },
});

const closeModal = () => {
  isModalOpen.value = false;
};

const submitForm = async () => {
  const botToken = process.env.VUE_APP_BOT_TOKEN;
  const chatId = process.env.VUE_APP_CHAT_ID;

  const message = ` *Новая анкета №${(userNumber.value =
    userNumber.value + 1)}*

👤 *Гость:* ${formData.value.userName}

💍 *Присутствие:* ${
    formData.value.attending === "Да"
      ? "✅ Буду на свадьбе!"
      : "❌ Не смогу прийти"
  }

 *Трансфер:* ${formData.value.transfer === "Да" ? " ✅ Нужен" : "❌ Не нужен"}

🥂 *Алкоголь:*
${
  [
    formData.value.alcohol.vine && " Алкоголь средней крепости",
    formData.value.alcohol.vodka && " Крепкие напитки",
    formData.value.alcohol.NotDrink && " Безалкогольные напитки",
  ]
    .filter(Boolean)
    .join(", ") || "❌ Не пьёт"
}

✨ *----------------* ✨`;

  try {
    await axios.post(`https://api.telegram.org/bot${botToken}/sendMessage`, {
      chat_id: chatId,
      text: message,
      parse_mode: "Markdown",
    });
    formData.value = {
      userName: "",
      attending: "",
      transfer: "",
      alcohol: {
        vine: false,
        vodka: false,
        NotDrink: false,
      },
    };
    isModalOpen.value = true;
  } catch (error) {
    console.error("Ошибка при отправке данных:", error);
    alert("Ошибка при отправке данных");
  }
};
</script>

<style scoped>
.form {
  margin-bottom: 110px;
  z-index: 4;
}
.form .container {
  margin: 0 auto;
  max-width: 1280px;
  padding: 0 40px;
  position: relative;
}
@media (min-width: 769px) and (max-width: 1024px) {
  .form .container {
    padding: 0 60px;
  }
}
@media (min-width: 435px) and (max-width: 770px) {
  .form .container {
    padding: 0 35px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form .container {
    padding: 0 20px;
  }
}
.form__wrapper {
  margin: 0 auto;
  max-width: 800px;
  width: 100%;
}
@media (min-width: 769px) and (max-width: 1024px) {
  .form__wrapper {
    max-width: 730px;
  }
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__wrapper {
    max-width: 600px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__wrapper {
    max-width: 320px;
  }
}
.form__title {
  border-bottom: 1px solid #665f55;
  color: #665f55;
  font-family: KyivType Sans;
  font-size: 46px;
  font-weight: 200;
  line-height: 56px;
  margin: 0 auto 20px;
  max-width: 140px;
  position: relative;
  text-align: center;
  width: 100%;
}
@media (min-width: 320px) and (max-width: 767px) {
  .form__title {
    font-size: 36px;
    line-height: 44px;
    margin-bottom: 20px;
    max-width: 180px;
  }
}
.form__wrap {
  margin: 0 auto;
  max-width: 800px;
  width: 100%;
}
@media (min-width: 769px) and (max-width: 1024px) {
  .form__wrap {
    max-width: 580px;
    padding: 10px 0 40px;
  }
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__wrap {
    max-width: 500px;
    padding: 10px 0 30px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__wrap {
    max-width: 300px;
    padding: 10px 0 30px;
  }
}
.form__text {
  color: #665f55;
  font-family: Open Sans, serif;
  font-size: 18px;
  font-weight: 300;
  line-height: 25px;
  margin-bottom: 40px;
  position: relative;
  text-align: center;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__text {
    font-size: 16px;
    line-height: 23px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__text {
    font-size: 14px;
    line-height: 21px;
  }
}
.form__text-subtitle {
  font-weight: 400;
  margin-bottom: 15px;
  text-align: left;
}
.form__text-mini {
  font-size: 12px;
  line-height: 18px;
  text-align: justify;
  text-indent: 15px;
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__text-mini {
    font-size: 10px;
    line-height: 16px;
  }
}
.form__name {
  margin-bottom: 20px;
}
.form__input {
  background: #665f55;
  border: none;
  color: #fff;
  font-family: Open Sans, sans-serif;
  font-size: 18px;
  font-weight: 300;
  line-height: 25px;
  margin-bottom: 5px;
  opacity: 1;
  outline: none;
  padding: 8px 0 8px 15px;
  width: 100%;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__input {
    font-size: 16px;
    line-height: 23px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__input {
    font-size: 14px;
    line-height: 16px;
  }
}
.form__input:focus,
.form__input:hover {
  box-shadow: 0 0 10px #665f55;
}
.form__input:focus {
  background-color: #665f55;
  color: #fff;
  opacity: 1;
  opacity: 0.7;
}
.form__input::placeholder {
  color: #fff;
  z-index: 1;
}
.form__yes {
  margin-bottom: 10px;
}
.form__yes-bottom {
  margin-bottom: 50px;
  position: relative;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__yes-bottom {
    margin-bottom: 40px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__yes-bottom {
    margin-bottom: 35px;
  }
}
.form__btn {
  background-color: #665f55;
  border: none;
  color: #fff;
  display: block;
  font-family: Open Sans, sans-serif;
  font-size: 18px;
  font-weight: 400;
  line-height: 25px;
  margin: 0 auto;
  max-width: 200px;
  padding: 10px 0;
  text-align: center;
  text-decoration: none;
  width: 100%;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form__btn {
    font-size: 16px;
    line-height: 23px;
    max-width: 170px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form__btn {
    font-size: 14px;
    line-height: 16px;
    max-width: 130px;
  }
}
.form__btn:focus,
.form__btn:hover {
  box-shadow: 0 0 10px #665f55;
}
.form__btn:focus {
  background-color: #665f55;
}
.form__wrapbtn {
  position: relative;
}
.form__error {
  position: absolute;
}
.form .error__text {
  color: #890c0c;
  font-family: Open Sans, sans-serif;
  font-size: 18px;
  font-weight: 400;
  line-height: 25px;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form .error__text {
    font-size: 16px;
    line-height: 23px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form .error__text {
    font-size: 14px;
    line-height: 16px;
  }
}
.form .checkboxes__row {
  display: flex;
  flex-direction: column;
}
.form .checkboxes__item {
  margin-bottom: 20px;
}
.form .checkbox.style-d {
  cursor: pointer;
  display: inline-block;
  padding-left: 30px;
  position: relative;
  -webkit-user-select: none;
  user-select: none;
}
.form .checkbox.style-d input {
  cursor: pointer;
  height: 0;
  opacity: 0;
  position: absolute;
  width: 0;
}
.form .checkbox.style-d input:checked ~ .checkbox__checkmark {
  background-color: #665f55;
}
.form .checkbox.style-d input:checked ~ .checkbox__checkmark:after {
  opacity: 1;
}
.form .checkbox.style-d:hover input ~ .checkbox__checkmark {
  box-shadow: 0 0 10px #665f55;
}
.form .checkbox.style-d:hover input:checked ~ .checkbox__checkmark {
  background-color: #665f55;
}
.form .checkbox.style-d .checkbox__checkmark {
  background: #665f55;
  border: 1px solid #665f55;
  height: 20px;
  left: 0;
  position: absolute;
  top: 2px;
  transition: background-color 0.25s ease;
  width: 20px;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form .checkbox.style-d .checkbox__checkmark {
    height: 17px;
    width: 17px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form .checkbox.style-d .checkbox__checkmark {
    height: 15px;
    top: 3px;
    width: 15px;
  }
}
.form .checkbox.style-d .checkbox__checkmark:after {
  background: #fff;
  content: "";
  height: 14px;
  left: 2px;
  opacity: 0;
  position: absolute;
  top: 2px;
  transition: opacity 0.25s ease;
  width: 14px;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form .checkbox.style-d .checkbox__checkmark:after {
    height: 11px;
    width: 11px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form .checkbox.style-d .checkbox__checkmark:after {
    height: 9px;
    width: 9px;
  }
}
.form .checkbox.style-d .checkbox__body {
  color: #665f55;
  font-family: Open Sans, serif;
  font-size: 18px;
  font-weight: 300;
  line-height: 25px;
}
@media (min-width: 435px) and (max-width: 770px) {
  .form .checkbox.style-d .checkbox__body {
    font-size: 16px;
    line-height: 23px;
  }
}
@media (min-width: 320px) and (max-width: 434px) {
  .form .checkbox.style-d .checkbox__body {
    font-size: 14px;
    line-height: 21px;
  }
}

/* Анимация */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Фон модалки */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(5px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

/* Модальное окно */
.modal {
  background: white;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  text-align: center;
  max-width: 350px;
  animation: scaleIn 0.3s ease;
}

/* Хедер с иконкой */
.modal__header {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.modal__icon {
  font-size: 40px;
  margin-bottom: 10px;
}

/* Текст */
.modal__text {
  margin: 10px 0;
  font-size: 16px;
  color: #333;
}

/* Кнопка */
.modal__button {
  margin-top: 15px;
  padding: 10px 20px;
  background: #4caf50;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 16px;
  transition: background 0.2s;
}

.modal__button:hover {
  background: #45a049;
}

/* Анимация увеличения */
@keyframes scaleIn {
  from {
    transform: scale(0.8);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}
</style>