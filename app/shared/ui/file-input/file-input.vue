<template>
  <label class="file-input" :class="{ 'has-error': error }">
    <PromtechIcon name="paperclip" :icon-size=25 />
    <span class="file-input__text">{{ displayText }}</span>
    <input
        type="file"
        class="file-input__native"
        @change="handleFileChange"
    />
  </label>
</template>

<script setup lang="ts">
import {PromtechIcon} from '@/shared/ui';

const props = withDefaults(defineProps<{
  modelValue: File | undefined;
  placeholder?: string;
  error?: boolean;
}>(), {
  placeholder: 'Прикрепить файл',
  error: false,
});

const emit = defineEmits<{
  (e: 'update:modelValue', value: File | undefined): void;
}>();

const displayText = computed(() => {
  return props.modelValue?.name || props.placeholder;
});

const handleFileChange = (event: Event) => {
  const input = event.target as HTMLInputElement;
  const files = input.files;

  if (files && files.length > 0) {
    emit('update:modelValue', files[0]);
  } else {
    emit('update:modelValue', undefined);
  }
};

</script>

<style scoped lang="scss">
.file-input {
  display: inline-flex;
  align-items: center;
  gap: 20px;
  cursor: pointer;
  width: 100%;

  color: $text-additional;
  @include link2;
}

.file-input.has-error {
  color: $error;
}

.file-input__native {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
}

</style>