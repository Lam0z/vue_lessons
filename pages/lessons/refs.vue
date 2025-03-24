<script setup>
const input = useTemplateRef("input");
onMounted(() => {
    input.value.addEventListener("click", () => {
        console.log("clicked");
    });
});

const lists = ref([1, 2, 3, 4, 5]);
const listRefs = useTemplateRef("listRefs");
onMounted(() => {
    console.log(listRefs.value);
    // listRefs.value.forEach((item, index) => {
    //     item.addEventListener("click", (e) => {
    //         // console.log(index, e.target.textContent);
    //         listRefs.value = listRefs.value.filter((i) => i != index);
    //     });
    // });
});
</script>

<template>
    <MainHeader>Ссылки на элементы шаблона</MainHeader>

    <LPart subtitle="Доступ к ссылкам ">
        <input type="text" class="form-control" ref="input" value="asdf" />
        {{ input }}
    </LPart>
    <!--  -->
    <LPart subtitle="Использование внутри v-for">
        <ul>
            <li v-for="list in lists" :key="list" ref="listRefs">
                {{ list }}
            </li>
        </ul>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
