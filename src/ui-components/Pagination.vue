<template>
  <nav aria-label="pagination">
    <ul class="pagination pagination-sm">
      <li
        v-for="pageNumber in totalPages"
        :key="pageNumber"
        class="pagination-item"
        :class="{ active: pageNumber == page }"
        @click="changePageHandler(pageNumber)"
      >
        <span class="page-link">{{ pageNumber }}</span>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Pagination",
  props: {
    totalPages: {
      type: Number,
      default: 0,
    },
    page: {
      type: Number,
      default: 1,
    },
  },
  methods: {
    changePageHandler(pageNumber) {
      this.$emit("changePage", pageNumber);
    },
  },
};
</script>

<style scoped>
.pagination-item {
  cursor: pointer;
}
</style>
