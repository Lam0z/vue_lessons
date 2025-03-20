<script setup>
const items = ref([{ message: "Foo" }, { message: "Bar" }]);

const myObject = reactive({
    title: "How to do lists in Vue",
    author: "Jane Doe",
    publishedAt: "2016-04-10",
});

const numbers = ref([1, 2, 3, 4, 5]);

const evenNumbers = computed(() => {
    return numbers.value.filter((n) => n % 2 === 0);
});

const sets = ref([
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
]);

function even(numbers) {
    return numbers.filter((number) => number % 2 === 0);
}
</script>

<template>
    <MainHeader>Отрисовка списков</MainHeader>

    <LPart subtitle="Отображение элементов массива через v-for ">
        <li v-for="({ message }, index) in items">
            {{ index }} - {{ message }}
        </li>
    </LPart>
    <!--  -->
    <LPart subtitle="Отображение свойств объекта через v-for ">
        <li v-for="(value, key, index) in myObject">
            {{ index }}.{{ key }},{{ value }}
        </li>
    </LPart>
    <!--  -->

    <LPart subtitle="v-for и <template>">
        <ul>
            <template v-for="(item, index) in 3">
                <li>{{ ++index }}</li>
                <li class="divider" role="presentation">
                    presentation - {{ index }}
                </li>
            </template>
        </ul>
    </LPart>
    <!--  -->
    <LPart subtitle="Отображение отфильтрованных/отсортированных результатов">
        <ul>
            <template v-for="(n, index) in evenNumbers">
                <li>{{ n }}</li>
            </template>
        </ul>
    </LPart>
    <!--  -->
    <LPart subtitle="Отображение отфильтрованных/отсортированных результатов">
        <ol v-for="n in sets">
            <li v-for="i in even(n)">
                {{ i }}
            </li>
        </ol>
    </LPart>
    <!--  -->
    <LPart subtitle="Отображение отфильтрованных/отсортированных результатов">
        <ol v-for="n in sets">
            <li v-for="i in even(n)">
                {{ i }}
            </li>
        </ol>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
