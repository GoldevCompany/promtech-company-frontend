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
          <p class="cases__text">
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
            <div class="case-card__inner">
                <h5 class="case-card__title">
                  {{ caseItem.title }}
                </h5>
                <h4 class="case-card__number">{{ caseItem.number }}</h4>
            </div>
            
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
        image: '/images/case-zaglushka.png'
    },
    {
        id: 2,
        number: '02',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/images/case-zaglushka.png'
    },
    {
        id: 3,
        number: '03',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/images/case-zaglushka.png'
    },
    {
        id: 4,
        number: '04',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/images/case-zaglushka.png'
    },
    {
        id: 5,
        number: '05',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/images/case-zaglushka.png'
    },
    {
        id: 6,
        number: '06',
        title: 'Кейс',
        text: 'Описание кейса, описание кейса',
        image: '/images/case-zaglushka.png'
    }
];
</script>

<style lang="scss" scoped>
.cases {
  margin-bottom: 128px;

  &__subtitle {
    @include headline6;
   
  }

  &__inner{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__title {
   @include headline3;
   white-space: nowrap;
  }

  &__text {
   @include text3;
   text-align: right;
  }

  &__grid{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px; 
    padding-top: 60px;
  }

  
  
}

.case-card {

  max-height: 300px;
  border: 1px solid $background-2;
  

  &__content {
    padding: 22px 31px 22px 20px;
  }

  &__inner{
    display: flex;
    justify-content: space-between;
  }

  &__title {
    @include headline5;
  }

  &__number {
    @include headline4;
  }

  &__text {
    @include text3;
    padding-top: 100px;
  }
}




</style>
