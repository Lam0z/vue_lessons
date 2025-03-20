<script setup>
const count = ref(0);
// console.log(count.value);

const obj = ref({
    nested: { count: 0 },
    arr: ["foo", "bar"],
});
function mutateDeeply() {
    // они будут работать, как и ожидалось.
    obj.value.nested.count++;
    obj.value.arr.push("baz");
}
const o = ref({ count: 0 });
console.log(o.value.count);
</script>

<template>
    <MainHeader>Основы реактивности</MainHeader>

    <LPart subtitle="Глубокая реактивность ">
        <div>
            <span> {{ obj }} </span>
        </div>
        <button class="btn btn-primary" @click="mutateDeeply">
            Change Obj
        </button>
    </LPart>
    <!--  -->
    <LPart subtitle="Объявление реактивного состояния">
        <span
            v-text="
                `import { ref } from 'vue' /

const count = ref(0)`
            "
        >
        </span>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
