<template>
  <h1>{{ myName }}</h1>
  <p>{{ counter }}</p>
  <button @click="plus">Plus</button>
  <button @click="minus">Minus</button>
  <p>{{ sana }} {{ oy }} {{ yil }}</p>

  <br />
  <hr />
  <input type="text" placeholder="Son kiriting" v-model="inputValue" />
  <button @click="showAlert">Sonni alertda chiqarish</button>
</template>
<script setup>
import { ref } from "vue";
import AWN from "awesome-notifications";

const date = new Date();

const sana = date.getDate();
const oy = date.getMonth();
const yil = date.getFullYear();

let myName = "IslomBek";

let counter = ref(-10);
let inputValue = ref("");

const notify = new AWN();

function plus() {
  counter.value++;
  notify.success("Son qo'shildi");
}

function minus() {
  counter.value--; //decrement
}

function showAlert() {
  alert(inputValue.value);
}
</script>
