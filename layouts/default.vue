<template>
    <header>
        <ul
            class="list-unstyled d-flex alert alert-primary justify-content-around wrap"
        >
            <li>
                <nuxt-link to="/">Home</nuxt-link>
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
    /* background: red; */
}
</style>
