<script setup lang="ts">

import {Button} from "~/shared";
</script>

<template>
  <div class="container our-production">
    <div class="our-production__label">Наша продукция</div>
    <div class="our-production__content">
      <div class="our-production__machinery">
        <div class="our-production__machinery-block">
          <div class="our-production__title">Каталог техники</div>
          <span>От буровых установок до обслуживающей техники — всё в одном месте</span>
          <div class="our-production__categories"></div>
        </div>
        <div class="our-production__machinery-view"></div>
      </div>
      <div class="our-production__details">
        <div class="our-production__details-image"></div>
        <div class="our-production__details-block">
          <div class="our-production__details-description">
            <p>ООО «ПромТехКомпани» поставляет оригинальные запасные части для горного и промышленного оборудования.</p>
            <p>Мы обеспечиваем бесперебойную работу вашей техники — от подземных самоходных машин до буровых установок. Все позиции проходят контроль качества и доступны со склада или под заказ.</p>
          </div>
          <div class="our-production__details-warehouse">
            <p>Перейдите в каталог, чтобы подобрать нужные запчасти.</p>
            <Button>Перейти на склад</Button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  .our-production {
    display: flex;
    flex-direction: column;
    position: relative;

    &__label {
      @include headline6
    }

    &__title {
      @include headline3
    }

    &__content {
      display: flex;
      flex-direction: column;

      gap: 20px;
    }

    &__machinery {
      display: flex;
      flex-direction: column;

      gap: 20px;

      @media (min-width: $breakpoint-tablet) {
        flex-direction: row;
      }
    }

    &__machinery-block {
      @media (min-width: $breakpoint-tablet) {
        flex: 1;
      }

      span {
        @include text3;
        color: $text-additional;
      }
    }

    &__categories {
      background-color: $accent;
      height: 300px;
      width: auto;
    }

    &__machinery-view {
      @media (min-width: $breakpoint-tablet) {
        flex: 1;
      }
      background-color: $accent;
      min-height: 300px;
    }

    &__details {
      display: flex;
      flex-direction: column-reverse;

      gap: 20px;

      @media (min-width: $breakpoint-tablet) {
        flex-direction: row;
      }
    }

    &__details-image{
      @media (min-width: $breakpoint-tablet) {
        flex: 1;
      }
      background-color: $accent;
      min-height: 300px;
    }

    &__details-block{
      @media (min-width: $breakpoint-tablet) {
        flex: 1;
      }

      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    &__details-description {
      p {
        margin: 0;
        @include text2;
      }

      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    &__details-warehouse {
      p {
        margin: 0;
        @include text3;
        color: $text-additional;
      }

      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
  }
</style>