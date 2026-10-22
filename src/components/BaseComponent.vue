<template>
  <div>Hello there! {{ combinedName }}</div>
  <div>
    <input type="text" v-model="firstName"> <input type="text" v-model="surname">
  </div>
  <div>
    {{ count }}
    <button @click="count++">Increment</button>
  </div>
</template>

<script setup>
import { computed, ref, watch, watchEffect } from 'vue';
const firstName = ref('');
const surname = ref('');

const combinedName = computed(
  () => `${firstName.value} ${surname.value}`
);

const count = ref(0);

watch(count, (prevValue) => {
  console.log('hello from watch');
  if(prevValue === 10) {
    console.log('we have 10!');
  }
});

watchEffect(() => {
  console.log('watchEffect!');
  if(count.value === 10) {
    console.log('we have a 10');
  }
})

const generateRandomNumbers = () => 
  Math.floor(Math.random(10) * 10);

  const $emit = defineEmits(['add', 'delete']);

  $emit('add');

  const props = defineProps({
    name: {
      type: String,
      required: true
    }
  })

</script>