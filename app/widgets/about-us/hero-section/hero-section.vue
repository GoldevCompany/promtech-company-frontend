<template>
  <section class="about-hero">
    <div class="about-hero__bg">
      <div class="container about-hero__content">
        <h1 class="about-hero__title">О компании</h1>
        <p class="about-hero__subtitle">
          Ваш надёжный партнёр в техническом <br>обслуживании и поставке горной техники
        </p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
.about-hero {
    
  &__bg {
    position:relative;
    width: 100%;
   
    background-image: url('/images/aboutUs-hero.png');
    background-size: cover;
    background-position: center;
    display: flex;
    
  }
  &__content {
    margin-top: 360px;
    
  }
  &__title {
    @include headline1;
    margin:0;
    
  }
  &__subtitle {
    @include text3;
    padding-top: 32px;
    padding-bottom: 32px;
    
  }
}
</style>