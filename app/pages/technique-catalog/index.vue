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
import type {Category} from '~/shared/types';

const route = useRoute();
const router = useRouter();

const catalogStore = useCatalogStore();
const { categories } = storeToRefs(catalogStore);

const initialId = route.query.category
    ? (route.query.category as Category['id'])
    : null;
const selectedCategoryId = ref<Category['id'] | null>(initialId);

await useAsyncData('categories', async () => {
    if (!categories.value?.length) {
        await catalogStore.getCategories();
    }
    return true;
});

watchEffect(() => {
    if (categories.value?.length && !selectedCategoryId.value) {
        selectedCategoryId.value = categories.value[0]?.id ?? null;
    }
});

watch(selectedCategoryId, (newId) => {
    router.replace({
        query: {
            category: newId
        }
    });
});

</script>