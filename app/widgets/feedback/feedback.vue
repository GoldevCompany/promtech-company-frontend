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
      <div class="feedback-container__form__narrow">
        <FileInput placeholder="Прикрепить карточку организации" :model-value="undefined"/>
        <FileInput placeholder="Прикрепить техническое задание" :model-value="undefined"/>
      </div>
      <TextField placeholder="Комментарий" />
    </div>
  </div>
</template>

<script setup lang="ts">
import {FileInput, TextField} from '@/shared'

</script>

<style scoped lang="scss">
.feedback-container {
  display: grid;
  padding: 30px 40px ;

  background-color: $error;

  grid-template-columns: 1fr;

  @media (min-width: $breakpoint-tablet) {
    grid-template-columns: 1fr 1fr;
    gap: 135px;
    padding: 46px 40px ;
  }

  @media (min-width: $breakpoint-desktop) {
    gap: 125px;
    padding: 128px 40px 60px 40px ;
  }

  &__label {
    @include headline3
  }

  &__form {
    &__narrow {
      display: flex;
      flex-direction: row;
    }
  }
}
</style>