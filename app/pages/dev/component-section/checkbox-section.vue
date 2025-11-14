<template>
  <section class="component-section">
    <h2 class="component-section__title">Checkbox Component</h2>
    <div class="demo-grid">
      <div class="demo-item">
        <Checkbox v-model="value"/>

        <p style="color: white; margin-top: 20px;">
          Текущее значение в поле: {{ value }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import {Checkbox} from '@/shared'

let value = ref(false);
</script>

<style scoped lang="scss">

</style>