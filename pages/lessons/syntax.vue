<script setup>
const vHtml = '<span style="color: red">Красный текст</span>';
const id = ref("");
onMounted(() => {
    id.value = Math.round(Math.random() * 1000);
});
const objectOfAttrs = {
    id: "container",
    class: "text-danger",
    style: "background-color:blue",
};
const myF = () => "myF message";
// const dynamicId = ;

const attributeName = "href";
const url = "https://www.google.com";
const href = "target";
const value = "blank";
</script>

<template>
    <MainHeader>Синтаксис шаблонов</MainHeader>

    <LPart subtitle="Текстовые интерполяции">
        <span v-text="`<span>Сообщение: {{ msg }}</span>`"> </span>
    </LPart>
    <!-- LP End -->
    <LPart subtitle="Сырой HTML">
        <span> {{ vHtml }}</span>
        <p><span v-html="vHtml"></span></p>
    </LPart>
    <!-- LP End -->
    <LPart subtitle="Атрибуты">
        <div :id>Случайное число, id сокращенный атрибут {{ id }}</div>
        <div v-bind="objectOfAttrs">Несколько аттрибутов в объекте</div>
    </LPart>
    <!-- LP End -->
    <LPart subtitle="Использование JavaScript-выражений">
        <div>if-else: {{ "/" ? "True" : "False" }}</div>
        <div>Вызов функции: {{ myF() }}</div>
    </LPart>
    <!-- LP End -->
    <LPart subtitle="Динамические аргументы">
        <a v-bind:[attributeName]="url"> Dynamic attribute </a>
        <p><a :[href]="value" href="/">Link </a></p>
    </LPart>
    <!-- LP End -->
</template>

<style scoped></style>
