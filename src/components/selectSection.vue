<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },

  methods: {
    emitSearchEvent() {
      this.$emit("performSearch");
    },
  },
};
</script>

<template>
  <div class="container">
    <select
      name=""
      id="optionsCard"
      v-model="store.archetypeText"
      @change="emitSearchEvent"
    >
      <option value="">Select Archetype</option>
      <option
        v-for="archetype in store.archetypesList"
        :key="archetype.archetype_name"
        :value="archetype.archetype_name"
      >
        {{ archetype.archetype_name }}
      </option>
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
