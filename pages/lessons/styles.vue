<script setup>
const vobj = '<div :class="{ "text-success": isActive }"></div>';
const varr = `const activeClass = ref('active')
const errorClass = ref('text-danger')`;
const styles = `<div :style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>`;
const activeClass = ref("text-info");
const errorClass = ref("text-danger");
const isActive = ref(false);
const hasError = ref(false);
const fz = ref(20);
const state = ref("grid");
const toggledActiveClass = computed(() =>
    isActive.value ? "toggle" : "noToggleDDDDD"
);
const r = ref({ r: 0, g: 0, b: 0 });
const getRandomvalue = () => {
    const colors = {
        r: Math.floor(Math.random() * 256),
        g: Math.floor(Math.random() * 256),
        b: Math.floor(Math.random() * 256),
    };
    r.value = colors;
};
</script>

<template>
    <MainHeader>Работа с классами и стилями</MainHeader>
    <LPart subtitle="Объектный синтаксис ">
        <div v-text="vobj"></div>
        <button
            :class="['btn', 'btn-primary', { 'text-success': isActive }]"
            @click="isActive = !isActive"
        >
            isActive - {{ isActive }}
        </button>
        <button
            class="underline"
            :class="['btn', 'btn-secondary', { 'text-danger': hasError }]"
            @click="hasError = !hasError"
        >
            hasError - {{ hasError }}
        </button>
    </LPart>
    <!--  -->

    <LPart subtitle="Синтаксис с массивом ">
        <div v-text="varr"></div>
        <button
            :class="[
                'btn btn-success',
                [isActive ? 'isActive' : 'noActive'],
                { 'my-text-style': isActive },
                [toggledActiveClass],
                activeClass,
                errorClass,
            ]"
        >
            activeClass, errorClass
        </button>
    </LPart>
    <!--  -->
    <LPart subtitle="Привязка инлайн-стилей ">
        <div v-text="styles"></div>
        <div class="styles">Lorem, ipsum dolor.</div>
        <button
            class="btn btn-primary"
            :style="[
                { fontSize: `${fz}px` },
                `backgroundColor: rgb(${r.r},${r.b},${r.g})`,
                `display: ${state}`,
            ]"
            @click="getRandomvalue"
        >
            {{ r }}
        </button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
