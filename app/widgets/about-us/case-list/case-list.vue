<template>
  <section class="cases">
    <div class="container">
      <div class="cases__header">
        <h6 class="cases__subtitle">
          Кейсы:
        </h6>
        <div class="cases__inner">
          <h3 class="cases__title">
            Опыт в деле
          </h3>
          <p class="cases__description">
            Реальные примеры выполненных проектов и решений для наших клиентов
          </p>
        </div>
      </div>
      <div class="cases__grid">
        <div
          v-for="caseItem in cases"
          :key="caseItem.id"
          class="case-card"
          :style="{ backgroundImage: 'url(' + caseItem.image + ')' }"
        >
          <div class="case-card__content">
            <h3 class="case-card__title">
              {{ caseItem.title }}
            </h3>
            <span class="case-card__number">{{ caseItem.number }}</span>
            <p class="case-card__text">
              {{ caseItem.text }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const cases = [
    {
        id: 1,
        number: '01',
        title: 'Восстановление моста',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case1.jpg'
    },
    {
        id: 2,
        number: '02',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case2.jpg'
    },
    {
        id: 3,
        number: '03',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case3.jpg'
    },
    {
        id: 4,
        number: '04',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case4.jpg'
    },
    {
        id: 5,
        number: '05',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case5.jpg'
    },
    {
        id: 6,
        number: '06',
        title: 'Разработка кассеты под требования Заказчика (бетономешалка)',
        text: 'Описание кейса, описание кейса',
        image: '/img/cases/case6.jpg'
    }
];
</script>

<style lang="scss" scoped>
.cases {

 

 

  &__subtitle {
    @include headline6;
   
  }

  &__title {
   @include headline3;
  }

  &__description {
   @include text3;
  }

  
}




</style>
