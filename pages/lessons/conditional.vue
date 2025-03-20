<script setup>
const condition = ref(false);
const sGroup = ref(true);
</script>

<template>
    <MainHeader>Условная отрисовка</MainHeader>

    <LPart subtitle="Простой пример ">
        <h1 v-if="condition">Vue восхитителен!</h1>
        <h1 v-else>О, нет 😢</h1>
        <button class="btn btn-primary" @click="condition = !condition">
            Switch
        </button>
    </LPart>
    <LPart subtitle="Условные группы с помощью v-if и <template> ">
        <template v-if="sGroup">
            <h1>Заголовок</h1>
            <p>Параграф 1</p>
            <p>Параграф 2</p>
        </template>
        <button class="btn btn-primary" @click="sGroup = !sGroup">
            Switch
        </button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
