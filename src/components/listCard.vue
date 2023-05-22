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
  <div class="container">
    <Cards
      v-for="cards in store.listCard"
      :key="cards.id"
      :pocketCard="cards"
      class="card"
    />
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/style/partial/variables.scss" as *;

.container {
  @include container-size;
  background-color: $bg-container;
  display: flex;
  flex-wrap: wrap;

  .card {
    flex: 0 0 20%;
    border: 5px solid white;
  }
}
</style>
