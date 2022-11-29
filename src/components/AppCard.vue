<script>
export default {
  name: "AppCard",
  props: {
    info: Object,
  },
};
</script>
<template>
  <main class="d-flex justify-content-around">
    <div class="text-center py-2 mb-2">
      <img class="img-fluid mt-2 p-2" :src="info.img" alt="" />
      <h5 class="mb-3">{{ info.name }}</h5>
      <h6>{{ info.category }}</h6>
      <span class="status">{{ info.status }}</span>
    </div>
  </main>
</template>
<style lang="scss" scoped>
.text-center {
  background-color: var(--primary-color);
  width: 200px;
  img {
    object-fit: contain;
  }
  h5 {
    color: white;
  }
  h6 {
    color: gray;
  }
  .status {
    font-size: 12px;
    color: grey;
  }
}
</style>
