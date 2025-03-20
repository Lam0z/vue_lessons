<template>
    <header>
        <ul
            class="h-100 w-100 list-unstyled d-flex alert alert-primary justify-content-around wrap"
        >
            <li>
                <nuxt-link to="/lessons/syntax" class=" ">Syntax</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/lessons/reactive" class=" ">Reactive</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/lessons/computed" class=" ">Computed</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/lessons/styles" class=" ">Styles</nuxt-link>
            </li>
        </ul>
    </header>
    <main>
        <div class="container">
            <slot></slot>
        </div>
    </main>
</template>

<script setup></script>

<style scoped>
header {
    display: flex;
    /* justify-content: center; */
    /* align-items: center; */
    min-height: 100vh;
}
ul {
    height: 100%;
}
</style>
