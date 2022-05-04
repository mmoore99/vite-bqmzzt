<template>
  <form @submit.prevent="submitHandler">
    <label
      >Name
      <input v-model="name" type="text" />
    </label>
    <button>Submit</button>
  </form>
</template>

<script setup>
import { computed } from 'vue';
const props = defineProps({
  modelValue: {
    type: String,
    default: '',
  },
});
const emit = defineEmits(['update:modelValue', 'submit']);

const name = computed({
  get() {
    return props.modelValue;
  },
  set(val) {
    emit('update:modelValue', val);
  },
});

function submitHandler() {
  console.log('Log from form component - submitHandler');
  emit('submit');
}

function testLog() {
  console.log('Log from form component');
}

defineExpose({
  submitHandler,
  testLog,
});
</script>
