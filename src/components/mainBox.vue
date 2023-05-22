<script>
import { store } from "../store";
import Cards from "./Cards.vue";

export default {
  components: {
    Cards,
  },

  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <Cards />
</template>

<style></style>
