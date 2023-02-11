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
import { ref, computed, reactive } from "vue";
//ref is used to make data reactive, and then computed, for computed functions
// setup attribute just means you don't have to use export default keywords.
//reactive and ref are interchangeable. Industry standard is ref.

// const name = ref("Justin");
// const greetings = `Hello ${name.value}`;// this is not reactive.
//console.log(greetings);
//to make functions reactive, use computed.

//reactive

const data = reactive({
  name: "Justin",
});

const greetings = computed(() => {
  //   if (!name.value.length) { // if using ref
  if (!data.name.length) {
    //if using reactive
    return "Who are you?";
  }

  //   return `Hello, ${name.value}`; //if using ref
  return `Hello, ${data.name}`; //if using reactive
});
</script>

<template>
  <!--if using ref-->
  <!-- <input type="text" v-model="name" /> -->
  <input type="text" v-model="data.name" />
  <!--If using reactive instead of ref.-->
  <!-- <h1>Hello, {{ name }}</h1> -->
  <h1>{{ greetings }}</h1>
</template>
