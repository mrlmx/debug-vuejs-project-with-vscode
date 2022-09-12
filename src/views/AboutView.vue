<script lang="ts" setup>
import { reactive, ref } from "vue";

const other = reactive([
  { name: "lmx", age: 18 },
  { name: "foo", age: 20 },
  { name: "bar", age: 12 },
]);
const count = ref(0);

const handlePlus = () => {
  console.log("plus before", count.value);
  count.value++;
  console.log("plus after", count.value);
};

const handleMinus = () => {
  console.log("minus before", count.value);
  count.value--;
  console.log("minus after", count.value);
};
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div>
      <p>{{ count }}</p>
      <button @click="handlePlus">plus</button>
      <button @click="handleMinus">minus</button>
      <hr style="margin: 20px 0" />
      <p v-for="item of other" :key="item.name">
        {{ item.name }}: {{ item.age }}
      </p>
    </div>
  </div>
</template>
