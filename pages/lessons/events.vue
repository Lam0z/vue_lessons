<script setup>
const name = ref("Nikita");
function greet(e) {
    // alert(`Hello, ${name.value}!`);
    console.log(e.target.tagName);
}
const say = (message) => {
    alert(message);
};

const addEvt = (msg, e) => {
    console.log(msg, e);
};
const once = () => {
    alert("Once");
};
const onDelete = () => {
    alert("onDelete");
};
const onRight = () => {
    alert("onRight");
};
</script>

<template>
    <MainHeader>Обработка событий</MainHeader>

    <LPart subtitle="Обработчик события в виде метода ">
        <button class="btn btn-primary" @click="greet">Hello</button>
    </LPart>
    <!--  -->
    <LPart subtitle="Вызов методов в инлайн-обработчиках ">
        <button class="btn btn-primary" @click="say('Hello Nick')">
            Say Hello
        </button>
    </LPart>
    <!--  -->
    <LPart subtitle="Доступ к событию через аргумент в инлайн-обработчиках ">
        <button class="btn btn-success" @click="addEvt('Message', $event)">
            Отправить
        </button>
    </LPart>
    <!--  -->
    <LPart subtitle="Модификаторы событий">
        <button class="btn btn-primary" @click.once="once">Once</button>
        <input
            type="text"
            class="form-control"
            placeholder="hello"
            @keydown.alt.delete="onDelete"
        />
        <button class="btn btn-primary" @click.right="onRight">
            Right click
        </button>
    </LPart>
    <!--  -->
</template>

<style scoped></style>
