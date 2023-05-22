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
  <div class="container">
    <select name="" id="optionsCard">
      <option value="">Alien</option>
      <option value="">Dragon</option>
      <option value="">Water</option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/style/partial/variables.scss" as *;

.container {
  @include container-size;

  #optionsCard {
    width: 200px;
    height: 30px;
    border-radius: 10px;
  }
}
</style>
