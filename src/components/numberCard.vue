<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="numCard">found {{ this.store.listCard.length }} cards</div>
</template>

<style lang="scss" scoped>
@use "../assets/style/partial/variables.scss" as *;
.numCard {
  @include container-size;
  font-size: 0.9rem;
  font-weight: 600;
  text-transform: uppercase;
  height: 30px;
  color: white;
  background-color: rgba(102, 101, 101, 0);
  border: 3px solid rgba(102, 101, 101, 0);
}
</style>
