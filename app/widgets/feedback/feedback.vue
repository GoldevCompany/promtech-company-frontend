<template>
  <div class="feedback-container">
    <div class="feedback-container__label">Свяжитесь с нами</div>
    <div class="feedback-container__form">
      <TextField placeholder="Фамилия и имя" />
      <TextField placeholder="Название организации" />
      <div class="feedback-container__form__narrow">
        <TextField placeholder="Электронная почта" />
        <TextField placeholder="Номер телефона" />
      </div>
      <div class="feedback-container__form__files">
        <FileInput placeholder="Прикрепить карточку организации" :model-value="undefined"/>
        <FileInput placeholder="Прикрепить техническое задание" :model-value="undefined"/>
      </div>
      <TextField placeholder="Комментарий" />
      <Checkbox v-model="agreement">
        <span>Согласен с <Link label="Правилами обработки персональных данных" to="#" variant="bold"/></span>
      </Checkbox>
      <Button
          label="Оставить заявку"
          trailingIcon="arrow"
          width="100%"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import {Checkbox, FileInput, Link, TextField, Button} from '@/shared'

let agreement = ref(false);

</script>

<style scoped lang="scss">
.feedback-container {
  display: grid;
  padding: 30px 40px ;
  gap:40px;
  background-color: $error;
  text-align: center;

  grid-template-columns: 1fr;

  @media (min-width: $breakpoint-tablet) {
    grid-template-columns: 1fr 1fr;
    gap: 135px;
    padding: 46px 40px ;
    text-align: start;
  }

  @media (min-width: $breakpoint-desktop) {
    gap: 125px;
    padding: 128px 40px 60px 40px ;
  }

  &__label {
    @include headline3
  }

  &__form {
    display: flex;
    flex-direction: column;
    gap: 20px;
    &__narrow {
      display: flex;
      flex-direction: row;
      gap: 20px;
    }
    &__files {
      display: flex;
      flex-direction: column;
      gap: 10px;

      @media (min-width: $breakpoint-tablet) {
        display: flex;
        flex-direction: row;
        gap: 20px;
      }
    }
  }
}
</style>