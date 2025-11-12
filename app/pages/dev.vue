<template>
    <div class="dev-page">
        <div class="dev-page__header">
            <h1>Компоненты проекта</h1>
            <p>Страница для тестирования и отладки UI компонентов</p>
        </div>

        <div class="dev-page__content">
            <!-- Link Component -->
            <section class="component-section">
                <h2 class="component-section__title">Link Component</h2>
                <p class="component-section__description">
                    Компонент ссылки с поддержкой вариантов стилей и иконок
                </p>

                <div class="demo-grid">
                    <div class="demo-item">
                        <h3>Regular variant</h3>
                        <Link to="/" label="Обычная ссылка" variant="regular" />
                    </div>

                    <div class="demo-item">
                        <h3>Bold variant</h3>
                        <Link to="/" label="Жирная ссылка" variant="bold" />
                    </div>

                    <div class="demo-item">
                        <h3>С иконкой arrow</h3>
                        <Link to="/" label="Ссылка со стрелкой" icon="arrow" />
                    </div>

                    <div class="demo-item">
                        <h3>С иконкой shopping-bag</h3>
                        <Link to="/" label="Корзина" icon="shopping-bag" />
                    </div>

                    <div class="demo-item">
                        <h3>Со слотом</h3>
                        <Link to="/">
                            Пользовательский текст через слот
                        </Link>
                    </div>

                    <div class="demo-item">
                        <h3>Только иконка</h3>
                        <Link to="/" icon="burger-menu" />
                    </div>

                    <div class="demo-item">
                        <h3>С большой иконкой (32px)</h3>
                        <Link to="/" label="Большая иконка" icon="arrow" iconSize="32px" />
                    </div>

                    <div class="demo-item">
                        <h3>С маленькой иконкой (12px)</h3>
                        <Link to="/" label="Маленькая иконка" icon="shopping-bag" iconSize="12px" />
                    </div>
                </div>

                <details class="code-details">
                    <summary>Показать код</summary>
                    <pre><code>&lt;Link to="/" label="Обычная ссылка" variant="regular" /&gt;
&lt;Link to="/" label="Жирная ссылка" variant="bold" /&gt;
&lt;Link to="/" label="Ссылка со стрелкой" icon="arrow" /&gt;
&lt;Link to="/" label="Большая иконка" icon="arrow" iconSize="32px" /&gt;
&lt;Link to="/" label="Маленькая иконка" icon="shopping-bag" iconSize="12px" /&gt;
&lt;Link to="/"&gt;Пользовательский текст через слот&lt;/Link&gt;</code></pre>
                </details>
            </section>

            <!-- PromtechIcon Component -->
            <section class="component-section">
                <h2 class="component-section__title">PromtechIcon Component</h2>
                <p class="component-section__description">
                    Компонент для отображения SVG иконок проекта
                </p>

                <div class="demo-grid">
                    <div class="demo-item">
                        <h3>arrow</h3>
                        <div class="icon-demo">
                            <PromtechIcon name="arrow" />
                        </div>
                        <code>name="arrow"</code>
                    </div>

                    <div class="demo-item">
                        <h3>burger-menu</h3>
                        <div class="icon-demo">
                            <PromtechIcon name="burger-menu" />
                        </div>
                        <code>name="burger-menu"</code>
                    </div>

                    <div class="demo-item">
                        <h3>paperclip</h3>
                        <div class="icon-demo">
                            <PromtechIcon name="paperclip" />
                        </div>
                        <code>name="paperclip"</code>
                    </div>

                    <div class="demo-item">
                        <h3>shopping-bag</h3>
                        <div class="icon-demo">
                            <PromtechIcon name="shopping-bag" />
                        </div>
                        <code>name="shopping-bag"</code>
                    </div>
                </div>

                <details class="code-details">
                    <summary>Показать код</summary>
                    <pre><code>&lt;PromtechIcon name="arrow" /&gt;
&lt;PromtechIcon name="burger-menu" /&gt;
&lt;PromtechIcon name="paperclip" /&gt;
&lt;PromtechIcon name="shopping-bag" /&gt;</code></pre>
                </details>
            </section>

            <!-- Button Component -->
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
                            iconSize="16"
                        />
                    </div>

                    <div class="demo-item">
                        <h3>Только иконка</h3>
                        <Button variant="primary" leadingIcon="burger-menu" iconSize="16px" />
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
        </div>
    </div>
</template>

<script setup lang="ts">
import { Link, PromtechIcon, Button } from '../shared'

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

<style scoped lang="scss">
.dev-page {
    min-height: 100vh;
    padding: 40px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;

    &__header {
        max-width: 1200px;
        margin: 0 auto 60px;
        text-align: center;

        h1 {
            @include headline3;
            margin-bottom: 16px;
        }

        p {
            @include text3;
            opacity: 0.9;
        }
    }

    &__content {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        gap: 60px;
    }
}

.component-section {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    border-radius: 16px;
    padding: 40px;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);

    &__title {
        @include headline4;
        margin-bottom: 12px;
        color: #fff;
    }

    &__description {
        @include text3;
        margin-bottom: 32px;
        opacity: 0.9;
    }
}

.demo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
    margin-bottom: 32px;
}

.demo-item {
    background: rgba(255, 255, 255, 0.15);
    padding: 24px;
    border-radius: 12px;
    border: 1px solid rgba(255, 255, 255, 0.2);
    transition: all 0.3s ease;

    &:hover {
        background: rgba(255, 255, 255, 0.2);
        transform: translateY(-2px);
        box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
    }

    h3 {
        @include headline5;
        margin-bottom: 16px;
        color: #fff;
    }

    code {
        @include text4;
        display: block;
        margin-top: 12px;
        padding: 8px 12px;
        background: rgba(0, 0, 0, 0.3);
        border-radius: 6px;
        color: #ffd700;
    }
}

.icon-demo {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 32px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 8px;
    font-size: 32px;

    :deep(svg) {
        width: 48px;
        height: 48px;
        fill: currentColor;
    }
}

.code-details {
    margin-top: 24px;
    background: rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    overflow: hidden;

    summary {
        @include text3;
        padding: 16px 24px;
        cursor: pointer;
        user-select: none;
        transition: background 0.2s ease;

        &:hover {
            background: rgba(0, 0, 0, 0.3);
        }
    }

    pre {
        margin: 0;
        padding: 24px;
        background: rgba(0, 0, 0, 0.4);
        overflow-x: auto;

        code {
            @include text4;
            color: #f8f8f2;
        }
    }
}
</style>

