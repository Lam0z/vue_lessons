<script setup>
const name = ref("Nikita");
function greet(e) {
    alert(`Hello, ${name.value}!`);
}
</script>

<template>
    <MainHeader>Обработка событий</MainHeader>

    <LPart subtitle="Обработчик события в виде метода ">
        <button class="btn btn-primary" @click="greet">Say Hello</button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
