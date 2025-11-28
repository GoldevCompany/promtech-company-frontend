<script setup lang="ts">
import {TechniqueCard} from '~/shared';
import type {MachineCard} from '~/shared/types';

const templateCardInfo: MachineCard = {
    id: '1',
    name: 'Одностреловые проходческие самоходные буровые установки РС3-05, РС3-01, РС3-10',
    photo: '/images/technique-card-image.png',
}

</script>

<template>
  <section class="component-section">
    <h2 class="component-section__title">
      TechniqueCard Component
    </h2>
    <div class="demo-grid">
      <div class="demo-item technique-grid-template">
        <TechniqueCard :card="templateCardInfo" />
        <TechniqueCard :card="templateCardInfo" />
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
$columns: 12;
$gap: 20px;

.technique-grid-template {
  $col-width: 295px;

  display: grid;
  grid-template-columns: repeat($columns, $col-width);
  gap: $gap;

  @media (min-width: $breakpoint-tablet) {
    $col-width: 350px;

    grid-template-columns: repeat($columns, $col-width);
  }

  @media (min-width: $breakpoint-desktop) {
    $col-width: 467px;

    grid-template-columns: repeat($columns, $col-width);
  }
}


</style>