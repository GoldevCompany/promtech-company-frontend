<template>
  <section class="component-section">
    <h2 class="component-section__title">Button Component</h2>
    <p class="component-section__description">
      Компонент кнопки с поддержкой вариантов стилей, размеров и иконок. Может работать как button или router-link.
    </p>

    <div class="demo-grid">
      <div class="demo-item">
        <h3>Primary Button (md)</h3>
        <Button label="Перейти на склад" variant="primary" size="md" />
      </div>

      <div class="demo-item">
        <h3>Primary с иконкой справа</h3>
        <Button 
          label="Оставить заявку" 
          variant="primary" 
          size="md" 
          trailingIcon="arrow"
        />
      </div>

      <div class="demo-item">
        <h3>Primary Small</h3>
        <Button label="Маленькая кнопка" variant="primary" size="sm" />
      </div>

      <div class="demo-item">
        <h3>С иконкой слева</h3>
        <Button 
          label="С иконкой" 
          variant="primary" 
          leadingIcon="shopping-bag"
          :iconSize=16
        />
      </div>

      <div class="demo-item">
        <h3>Только иконка</h3>
        <Button variant="primary" leadingIcon="burger-menu" :iconSize=16 />
      </div>

      <div class="demo-item">
        <h3>Кастомный gap (8px)</h3>
        <Button 
          label="Большой gap" 
          variant="primary" 
          trailingIcon="arrow" 
          iconGap="8px"
        />
      </div>

      <div class="demo-item">
        <h3>Ширина 100%</h3>
        <Button 
          label="Во всю ширину" 
          variant="primary" 
          width="100%"
        />
      </div>

      <div class="demo-item">
        <h3>Фиксированная ширина 250px</h3>
        <Button 
          label="250px" 
          variant="primary" 
          width="250px"
          trailingIcon="arrow"
        />
      </div>

      <div class="demo-item">
        <h3>С обработчиком @click</h3>
        <Button 
          label="Нажми меня" 
          variant="primary" 
          @click="handleClick"
        />
      </div>

      <div class="demo-item">
        <h3>Submit с обработчиком</h3>
        <Button 
          label="Отправить форму" 
          variant="primary" 
          type="submit"
          @click="handleSubmit"
        />
      </div>

      <div class="demo-item">
        <h3>С параметром</h3>
        <Button 
          label="Удалить #123" 
          variant="primary" 
          @click="deleteItem(123)"
        />
      </div>

      <div class="demo-item">
        <h3>Disabled (клик не работает)</h3>
        <Button 
          label="Отправить заявку" 
          variant="primary" 
          disabled 
          trailingIcon="arrow"
          @click="handleClick"
        />
      </div>

      <div class="demo-item">
        <h3>Как router-link (без @click)</h3>
        <Button label="Перейти на главную" variant="primary" to="/" />
      </div>
    </div>

    <details class="code-details">
      <summary>Показать код</summary>
      <pre><code>&lt;Button label="Перейти на склад" variant="primary" size="md" /&gt;
&lt;Button label="Оставить заявку" variant="primary" trailingIcon="arrow" /&gt;
&lt;Button label="Маленькая кнопка" variant="primary" size="sm" /&gt;
&lt;Button label="С иконкой" variant="primary" leadingIcon="shopping-bag" /&gt;
&lt;Button variant="primary" leadingIcon="burger-menu" iconSize="16px" /&gt;
&lt;Button label="Большой gap" variant="primary" trailingIcon="arrow" iconGap="8px" /&gt;
&lt;Button label="Во всю ширину" variant="primary" width="100%" /&gt;
&lt;Button label="250px" variant="primary" width="250px" trailingIcon="arrow" /&gt;
&lt;!-- С обработчиком клика --&gt;
&lt;Button label="Нажми меня" variant="primary" @click="handleClick" /&gt;
&lt;Button label="Отправить форму" type="submit" @click="handleSubmit" /&gt;
&lt;Button label="Удалить #123" @click="deleteItem(123)" /&gt;
&lt;!-- Disabled - клик не сработает --&gt;
&lt;Button label="Отключенная" disabled @click="handleClick" /&gt;
&lt;!-- Router navigation --&gt;
&lt;Button label="Перейти на главную" variant="primary" to="/" /&gt;</code></pre>
    </details>
  </section>
</template>

<script setup lang="ts">
import { Button } from '@/shared'

// Обработчики для демонстрации
const handleClick = (event: MouseEvent) => {
  alert('Кнопка нажата!')
  console.log('Click event:', event)
}

const handleSubmit = () => {
  alert('Форма отправлена!')
}

const deleteItem = (id: number) => {
  alert(`Удаление элемента ${id}`)
}
</script>

