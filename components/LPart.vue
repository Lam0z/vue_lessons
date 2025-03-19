<script setup>
defineProps({
    subtitle: {
        type: String,
        default: "Subtitle",
        required: false,
    },
});
</script>
<template>
    <MainHeader />
    <div class="lesson-content">
        <h2>{{ subtitle }}</h2>
        <div class="lesson-description">
            <div class="alert alert-success">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
.lesson-content {
    margin: 2rem 0 0;
    padding: 1rem 0 0;
    border-top: 1px solid var(--border-color);
    /* border-bottom: 1px solid var(--border-color); */
}
</style>
