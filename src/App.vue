<!-- <script>
export default {
  data() {
    return {
      name: "Justin",
    };
  },
  computed: {
    greetings() {
      if (!this.name.length) {
        return "Who are you?";
      }

      return `Hello, ${this.name}`;
    },
  },
};
</script>

<template>
  <h1>Hello, {{ name }}</h1>
</template> -->

<script setup>
import { ref, computed } from "vue";
// setup attribute just means you don't have to use export default keywords.

const name = ref("Justin");
// const greetings = `Hello ${name.value}`;// this is not reactive.
//console.log(greetings);
//to make functions reactive, use computed.

const greetings = computed(() => {
  if (!name.value.length) {
    return "Who are you?";
  }

  return `Hello, ${name.value}`;
});
</script>

<template>
  <input type="text" v-model="name" />
  <!-- <h1>Hello, {{ name }}</h1> -->
  <h1>{{ greetings }}</h1>
</template>
