<template>
  <div>Hello there!</div>
  <div>
    {{ count }}
    <button @click="count++">Increment</button>
  </div>
</template>

<script setup>
import { ref, watch, watchEffect } from 'vue';

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


</script>