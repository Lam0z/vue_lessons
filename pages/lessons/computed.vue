<script setup>
const author = ref({
    name: "John Doe",
    books: [
        "Vue 2 - Advanced Guide",
        "Vue 3 - Basic Guide",
        "Vue 4 - The Mystery",
    ],
});

const publishedBooks = computed(() => {
    return author.value.books.length > 2 ? "Yes" : "No";
});
const calculateBooksMessage = () => {
    return author.value.books.length > 1 ? "Yes" : "No";
};
console.log(publishedBooks.value);
</script>

<template>
    <MainHeader>Вычисляемые свойства</MainHeader>

    <LPart subtitle="Простой пример ">
        <div>Есть опубликованные книги:</div>
        <div>{{ publishedBooks }}</div>
        <button class="btn btn-primary" @click="author.books.pop()">
            Cut a book
        </button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
