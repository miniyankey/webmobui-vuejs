<script setup>
import { computed, ref, watch, defineModel } from "vue";
const temp = ref(0)
const kelvin = defineModel("kelvin", {
  set: (val) => temp.value = Number(val),
  get: () => Math.round(temp.value * 100) / 100
})
const celsius = defineModel("celsius", {
  get: () => Math.round((temp.value - 273.15) * 100) / 100,
  set: (val) => {
    temp.value = val + 273.15;
  }
});
const fahrenheit = defineModel("fahrenheit", {
  get: () => Math.round(((temp.value - 273.15) * (9 / 5) + 32) * 100) / 100,
  set: (val) => temp.value = (val - 32) * (5 / 9) + 273.15
});
import BaseInputNumber from "./components/BaseInputNumber.vue";

</script>

<template>
  <h1>Choisissez votre température</h1>
  <BaseInputNumber label="k" v-model="kelvin" />
  <BaseInputNumber label="°C" v-model="celsius" />
  <BaseInputNumber label="°F" v-model="fahrenheit" />
</template>

<style></style>
