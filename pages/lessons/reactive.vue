<script setup>
const count = ref(0);
console.log(count.value);
</script>

<template>
    <MainHeader>Основы реактивности</MainHeader>

    <LPart subtitle="Объявление реактивного состояния">
        <span
            v-text="
                `import { ref } from 'vue' /

const count = ref(0)`
            "
        >
        </span>
    </LPart>
</template>

<style scoped></style>
