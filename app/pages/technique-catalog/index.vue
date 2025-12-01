<template>
  <div class="container">
    <h1
      class="page-info__title"
      :style="{ 'margin-bottom': '20px' }"
    >
      Техника
    </h1>
    <CategoryPicker
      v-model="selectedCategoryId"
      :categories="categories"
    />
    <ul>
      <li
        v-for="n in 10"
        :key="n"
        :style="{ 'margin-bottom': '20px' }"
      >
        <NuxtLink
          :to="`/components-catalog/${n}`"
          class="section-label"
        >
          Техника {{ n }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import {CategoryPicker} from '~/widgets/technique-catalog';
import {useCatalogStore} from '~/entities';

const catalogStore = useCatalogStore();

const { categories } = storeToRefs(catalogStore);
const selectedCategoryId = ref<number | string | null>(categories.value?.[0]?.id ?? null);

await useAsyncData('categories', async () => {
    if (!categories.value?.length) {
        await catalogStore.getCategories();
        if (!selectedCategoryId.value && categories.value?.length) {
            selectedCategoryId.value = categories.value[0]?.id ?? null;
        }
    }
    return true;
});

</script>