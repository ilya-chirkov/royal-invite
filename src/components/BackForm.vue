<template>
  <div class="form">
    <div class="container">
      <div class="form__wrapper">
        <div>
          <h3 class="form__title">Form</h3>
        </div>
        <div>
          <div class="form__textwrap">
            <p class="form__text">Просьба заполнить анкету до 01 марта</p>
          </div>
        </div>
        <div>
          <form class="form__wrap" id="telegramForm">
            <div class="form__name">
              <p class="form__text form__text-subtitle">Ваше Имя и Фамилия:</p>
              <input
                class="form__input"
                type="text"
                name="user_name"
                id="user-name-input"
                placeholder="Введите свое Имя и Фамилию"
                autocomplete="off"
                value=""
              />
              <p class="form__text form__text-mini">
                Если вы будете в компании своего спутника/спутницы, просим
                дополнительно внести его/ее данные в графу.
              </p>
            </div>
            <div class="form__yes">
              <p class="form__text form__text-subtitle">
                Планируете ли Вы присутствовать на свадьбе?
              </p>
              <div class="checkboxes__row">
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="yes"
                    ><input type="radio" id="yes" name="attending" value="Да" />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Да, буду на свадьбе</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="no"
                    ><input type="radio" id="no" name="attending" value="Нет" />
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
                Необходим ли Вам трансфер?
              </p>
              <div class="checkboxes__row">
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="transferYes"
                    ><input
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
                      type="checkbox"
                      id="alcChoice1"
                      name="alcohol"
                      value="Вино"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Вино</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice2"
                    ><input
                      type="checkbox"
                      id="alcChoice2"
                      name="alcohol"
                      value="Шампанское"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Шампанское</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice3"
                    ><input
                      type="checkbox"
                      id="alcChoice3"
                      name="alcohol"
                      value="Виски"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Виски</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice4"
                    ><input
                      type="checkbox"
                      id="alcChoice4"
                      name="alcohol"
                      value="Коньяк"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Коньяк</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice5"
                    ><input
                      type="checkbox"
                      id="alcChoice5"
                      name="alcohol"
                      value="Водка"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Водка</p></label
                  >
                </div>
                <div class="checkboxes__item">
                  <label class="checkbox style-d" for="alcChoice6"
                    ><input
                      type="checkbox"
                      id="alcChoice6"
                      name="alcohol"
                      value="Безалкогольные напитки"
                    />
                    <div class="checkbox__checkmark"></div>
                    <p class="checkbox__body">Безалкогольные напитки</p></label
                  >
                </div>
              </div>
            </div>
            <div class="form__wrapbtn">
              <button class="form__btn" type="submit">Отправить</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>