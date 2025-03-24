<script setup>
const v = ref("asf");
const message = ref("hello wrold");
const checked = ref(false);
const checkedNames = ref([]);
const picked = ref(null);
const selected = ref("A");

const options = ref([
    { text: "Один", value: "A" },
    { text: "Два", value: "B" },
    { text: "Три", value: "C" },
]);
const pickeds = ref();
// const changeV = (e) => (v.value = e.target.value);
</script>

<template>
    <MainHeader>Работа с формами</MainHeader>

    <LPart subtitle="Текст ">
        <div class="output">Output: {{ v }}</div>
        <input type="text" class="form-control" v-model="v" />
    </LPart>
    <!--  -->
    <LPart subtitle="Многострочный текст ">
        <span>Many rows text</span>
        <p style="white-space: pre-line">{{ message }}</p>
        <textarea
            v-model="message"
            placeholder="input some words"
            class="form-control"
        ></textarea>
    </LPart>
    <!--  -->
    <LPart subtitle="Чекбоксы ">
        <input type="checkbox" id="checkbox" v-model="checked" />
        <label for="checkbox">{{ checked }}</label>
    </LPart>
    <!--  -->
    <LPart subtitle="Чекбоксы ">
        <div>Отмеченные имена: {{ checkedNames }}</div>

        <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
        <label for="jack">Jack</label>

        <input type="checkbox" id="john" value="John" v-model="checkedNames" />
        <label for="john">John</label>

        <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
        <label for="mike">Mike</label>
    </LPart>
    <!--  -->
    <LPart subtitle="Радиокнопки ">
        <div>picked {{ picked }}</div>
        <input type="radio" id="one" value="Один" v-model="picked" />
        <label for="one">Один</label>

        <input type="radio" id="two" value="Два" v-model="picked" />
        <label for="two">Два</label>
    </LPart>
    <!--  -->
    <LPart subtitle="Выпадающие списки ">
        <select v-model="selected">
            <option v-for="option in options" :value="option.value">
                {{ option.text }}
            </option>
        </select>

        <div>Выбрано: {{ selected }}</div>
    </LPart>
    <!--  -->
    <LPart subtitle="Привязка значений ">
        <div>{{ pickeds }}</div>
        <input type="radio" v-model="pickeds" value="a" />
        <input type="radio" v-model="pickeds" value="b" />
    </LPart>
    <!--  -->
    <LPart subtitle="Модификаторы ">
        <div>{{ pickeds }}</div>
        <input type="radio" v-model="pickeds" value="a" />
    </LPart>

    <!--  -->
</template>

<style scoped></style>
