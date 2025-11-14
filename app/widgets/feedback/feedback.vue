<template>
  <div class="feedback-container" :style="backgroundStyles">
    <div class="feedback-container__label">Свяжитесь с нами</div>
    <div class="feedback-container__form">
      <TextField placeholder="Фамилия и имя" v-model="name"/>
      <TextField placeholder="Название организации" v-model="organisation"/>
      <div class="feedback-container__form__narrow">
        <TextField placeholder="Электронная почта" v-model="email"/>
        <TextField placeholder="Номер телефона" v-model="phone" :mask="'+7 (###) ### ## ##'"/>
      </div>
      <div class="feedback-container__form__files">
        <FileInput placeholder="Прикрепить карточку организации" v-model="fileOrgCard"/>
        <FileInput placeholder="Прикрепить техническое задание" v-model="fileTask"/>
      </div>
      <TextField placeholder="Комментарий" v-model="comment"/>
      <Checkbox v-model="agreement">
        <span>Согласен с <Link label="Правилами обработки персональных данных" to="#" variant="bold"/></span>
      </Checkbox>
      <Button
          label="Оставить заявку"
          trailingIcon="arrow"
          width="100%"
          :disabled="isButtonDisabled"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import {Checkbox, FileInput, Link, TextField, Button} from '@/shared'

let name = ref('');
let organisation = ref('');
let email = ref('');
let phone = ref('');
let comment = ref('');

const fileOrgCard = ref<File | undefined>(undefined);
const fileTask = ref<File | undefined>(undefined);

let agreement = ref(false);

const isButtonDisabled = computed(() => {
  return (
      name.value.trim() === '' ||
      organisation.value.trim() === '' ||
      email.value.trim() === '' ||
      phone.value.trim() === '' ||
      !fileOrgCard.value ||
      !agreement.value
  );
});

const $img = useImage();

const backgroundStyles = computed(() => {
  const imageUrl = $img('/images/mineral.png', {
    format: 'webp',
    quality: 80,
  })

  return {
    '--bg-image': `url('${imageUrl}')`
  }
})
</script>

<style scoped lang="scss">
.feedback-container {
  display: grid;
  grid-template-columns: 1fr;

  padding: 30px 40px ;
  gap:40px;
  text-align: center;

  position: relative;
  overflow: hidden;
  z-index: 0;


  &::before {
    content: '';
    position: absolute;
    inset: 0;
    z-index: -2;
    opacity: 59%;

    background-image: var(--bg-image);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    object-fit: cover;

    filter: brightness(0.4) contrast(1) saturate(0.1);
    transform: rotate(180deg) scale(1.5);
  }

  &::after {
    content: '';
    position: absolute;
    inset: 0;
    z-index: -1;

    background-image: linear-gradient(to right, #2D2E34FF 0%, #2D2E3400 9%, #2D2E3400 89%, #2D2E34FF 100%);
  }

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