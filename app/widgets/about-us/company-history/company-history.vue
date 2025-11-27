<template>
  <section class="company-history">
    <div class="container">
      <div class="company-history__header">
        <h6 class="company-history__subtitle">
          История компании:
        </h6>  
        <h3 class="company-history__title">
          Годы надежности
        </h3>
      </div>
      <ul class="company-history__list">
        <li
          v-for="item in history"
          :key="item.year"
          :class="[
            'company-history__item',
            { 'company-history__item--active': item.active }
          ]"
        >
          <div class="company-history__inner">
            <div class="company-history__year">
              {{ item.year }}
            </div>

            <div class="company-history__content">
              <div class="company-history__text">
                {{ item.title }}
              </div>

              <p
                v-if="item.description"
                class="company-history__description"
              >
                {{ item.description }}
              </p>
            </div>
          </div>
          <Button
            class="company-history__icon-btn"
            trailing-icon="arrow"
            size="sm"
            :icon-size="30"
          />
        </li>
      </ul>
    </div>
  </section>
</template>

<script setup lang="ts">
import Button from '~/shared/ui/Button/button.vue'

const history = [
    { year: '2008', title: 'Начало пути' , description:
      'Описание для 2008' },
    {
        year: '2015',
        title: 'Стратегический выбор',
        description:
      'Партнёрство с производителем подземной техники ООО «Амкодор-Инвар»',
        active: true
    },
    { year: '2016', title: 'Первые результаты', description:
      'Описание для 2016' },
    { year: '2022', title: 'Новая технологическая линия', description:
      'Описание для 2022' },
    { year: '2023', title: 'Выход на ключевые проекты' , description:
      'Описание для 2023'},
    { year: '2024', title: 'Укрепление сервисной базы' , description:
      'Описание для 2024'}
];
</script>

<style scoped lang="scss">
.company-history {
  margin-top: 68px;
  background-color: $background-2;
  color: $background-1;

  &__subtitle {
    @include headline6;

    padding-top: 60px;
  }

  &__title {
    @include headline3;

    padding-top: 44px;

    @media (min-width: $breakpoint-tablet) {
      gap: 44px;
    }

    @media (min-width: $breakpoint-desktop) {
      gap: 60px;
    }
  }

  &__list {
    display: flex;
    flex-direction: column;
    padding-top: 60px;
  }

  &__item {
    display: flex;
    border-top: 1px solid $background-4;
    padding: 20px;
    transition: background-color .3s ease, color .3s ease;
  }


  &__inner {
    display: flex;
    gap: 26px;
    align-items: center;

    @media (min-width: $breakpoint-tablet) {
      gap: 60px;
    }

    @media (min-width: $breakpoint-desktop) {
      gap: 105px;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
  }

  &__year {
    @include headline3;

    color: $background-4;
    transition: color .3s;
  }

  &__text {
    @include headline5;

    color: $background-4;
    padding-top: 20px;
    transition: color .3s;
  }

  &__description {
    @include text3;

    max-width: 357px;
    color: $text-main;
    opacity: 0;
    overflow: hidden;
    transition: all .40s ease;
  }

  &__icon-btn {
    background: none !important;
    border: none !important;
    padding: 0;
    color: $accent;
    margin-left: auto;
    transition: color .25s ease, transform .25s ease;
  }


  &__item:hover {
    background-color: $accent;

    .company-history__year,
    .company-history__text,
    .company-history__description,
    .company-history__icon-btn {
      color: $text-main;
    }

    .company-history__description {
      opacity: 1;
      padding-top: 28px;

      @media (min-width: $breakpoint-tablet) {
        padding-top: 64px;
      }

      @media (min-width: $breakpoint-desktop) {
        padding-top: 64px;
      }
    }

    .company-history__icon-btn {
      transform: rotate(180deg);
    }
  }
}
</style>
