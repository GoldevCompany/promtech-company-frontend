<template>
  <div class="default-layout">
    <Header />
    <main class="main-content">
      <slot />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import {Header} from '../header'
import {Footer} from '../footer';
</script>

<style lang="scss">
.default-layout {
  // 1. Превращаем layout в flex-контейнер
  display: flex;
  // 2. Устанавливаем направление основной оси в вертикальное (сверху вниз)
  flex-direction: column;
  // 3. Задаем минимальную высоту, равную 100% высоты видимой области окна браузера
  min-height: 100vh;
}

.main-content {
  // 4. Разрешаем этому блоку растягиваться, чтобы занять все доступное пространство
  // flex: 1; - это сокращение для flex-grow: 1; flex-shrink: 1; flex-basis: 0%;
  flex: 1;
}
</style>