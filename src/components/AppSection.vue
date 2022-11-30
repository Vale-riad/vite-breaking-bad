<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
export default {
  name: "AppSection",
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
};
</script>
<template>
  <div class="container-lg py-5 px-5">
    <div class="container-sm">
      <h6 class="py-3">Found {{ store.characters.length }} characters</h6>
    </div>
    <div class="container-sm row justify-content-around">
      <AppCard
        v-for="character in store.characters"
        class="my-col m-2"
        :info="character"
      />
    </div>
  </div>
</template>
<style lang="scss" scoped>
.container-lg {
  background-color: var(--secondary-color);
}

.container-sm {
  flex-wrap: wrap;
  h6 {
    color: white;
    background-color: #212529;
  }
  .my-col {
    width: calc(100% - 32px);
    @include media-breakpoint-up(sm) {
      width: calc(50% - 32px);
    }
    @include media-breakpoint-up(md) {
      width: calc((100% / 3) - 32px);
    }
    @include media-breakpoint-up(lg) {
      width: calc(20% - 32px);
    }
  }
}
</style>
