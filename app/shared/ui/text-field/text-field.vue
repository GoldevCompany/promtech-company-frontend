<template>
  <div class="text-input">
    <input
        type="text"
        class="text-input__field"
        :value="modelValue"
        :placeholder="placeholder"
        @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
        v-maska :data-maska="mask"
    />
  </div>
</template>

<script setup lang="ts">
import { vMaska } from 'maska/vue'

withDefaults(defineProps<{
  modelValue: string;
  placeholder?: string;
  mask?: string;
}>(), {
  placeholder: '',
  modelValue: '',
  mask: '',
});

defineEmits<{
  (e: 'update:modelValue', value: string): void;
}>();

</script>

<style scoped lang="scss">
.text-input {
  width: 100%;
  position: relative;

  &__field {
    width: 100%;
    display: block;

    background-color: transparent;
    border: none;
    border-bottom: 1px solid white;
    padding: 8px 2px;

    @include link2;
    color: $text-main;

    &:focus {
      outline: none;
    }

    &::placeholder {
      @include link2;
      color: $text-additional;
    }
  }
}


</style>