<script>
export default {
  props: {
    pocketCard: Object,
  },
};
</script>

<template>
  <div class="setCard">
    <img
      :src="pocketCard.card_images[0].image_url_small"
      :alt="pocketCard.name"
    />
    <div class="cardName">{{ pocketCard.name }}</div>
    <div class="species">{{ pocketCard.archetype }}</div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/style/partial/variables.scss" as *;

.setCard {
  background-color: rgb(245, 154, 8);
  padding: 0 0 0.5rem 0.8rem;

  img {
    width: 100%;
  }

  .cardName,
  .species {
    font-size: 0.6rem;
    font-weight: 800;
    text-align: center;
    text-transform: uppercase;
  }

  .cardName {
    color: white;
    line-height: 2rem;
  }
}
</style>
