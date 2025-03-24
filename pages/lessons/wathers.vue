<script setup>
const x = ref(0);
const y = ref(0);

const obj = reactive({ count: 0 });

watch(x, (newX) => {
    console.log(`x is ${newX}`);
});

watch(
    () => x.value - y.value,
    (sum) => {
        console.log(`сумма x + y равна: ${sum}`);
    }
);

watch(obj, (newValue, oldValue) => {
    console.log(newValue.count);
    console.log(oldValue.count);
});
</script>

<template>
    <MainHeader>Наблюдатели</MainHeader>

    <LPart subtitle="Простой пример ">
        <!-- <div>{{ x }}</div>     -->
        <button class="btn btn-primary" @click="x++">{{ x }}</button>
        <button class="btn btn-primary" @click="y++">{{ y }}</button>
        <button class="btn btn-primary" @click="obj.count++">
            {{ obj.count }}
        </button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
