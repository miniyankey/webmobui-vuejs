<script setup>
import { defineModel, defineProps } from 'vue';
const model = defineModel();
defineProps({
    label: String
})
</script>
<template>
    <div class="temp">
        <label>{{ label }}</label>
        <input type="number" v-model="model">
    </div>
</template>
<style scoped>
input {
    border: none;
    background-color: rgb(116, 120, 179);
    padding: 16px;
    border-radius: 24px;
    color: rgb(231, 231, 242);
}

.temp{
    display: flex;
    align-items: center;
    gap: 16px;
}

label {
    font-size: 1.5rem;
    text-align: left;
    color: rgb(183, 190, 220);
}
</style>