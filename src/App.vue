<template>
  <div>Hello there, {{ name }}!</div>
  <Form v-model="name" @submit="submitForm" ref="formRef" />
</template>

<script setup>
import { ref } from 'vue';
import Form from './components/Form.vue';

const name = ref('');
const formRef = ref(null);

function submitForm() {
  console.log(name.value);
  console.log('formRef', formRef.value);
  debugger;
}
</script>
