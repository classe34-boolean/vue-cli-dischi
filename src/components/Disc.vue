<template>
  <div class="disc p-3 text-center">
      <img :src="item.poster" :alt="item.title" class="mb-3">
      <h2 class="mb-4">{{ item.title }}</h2>
      <h3>{{ item.author }}</h3>
      <h4>{{ item.year }}</h4>
  </div>
</template>

<script>
export default {
    name: "Disc",
    props: {
        item: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/styles/variables';

    .disc {
        width: calc(100% / 5 - 2rem);
        margin: 1rem;
        background-color: $light-color;

        img {
            width: 100%;
        }

        h2 {
            font-size: 18px;
            text-transform: uppercase;
        }

        h3 {
            font-size: 18px;
            color: $font-color;
        }

        h4 {
            font-size: 15px;
            color: $font-color;
        }
    }
</style>