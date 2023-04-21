<template>
  <div class="btn-group">
    <PrimaryButton
      v-for="button in filterButtons"
      :key="button.name"
      type="button"
      @click="filterHandler(button.name)"
      :class="[filterName == button.name ? 'btn-dark' : 'btn-outline-dark']"
    >
      {{ button.title }}
    </PrimaryButton>
  </div>
</template>

<script>
export default {
  props: {
    updateFilterHandler: {
      type: Function,
      required: true,
    },
    filterName: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      filterButtons: [
        { name: "all", title: "Barcha kinolar" },
        { name: "popular", title: "Mashxur kinolar" },
        { name: "mostViewers", title: "Eng ko'p ko'rilgan kinolar" },
      ],
      filter: "all",
    };
  },
  methods: {
    filterHandler(filter) {
      this.filter = filter;
      this.updateFilterHandler(this.filter);
    },
  },
};
</script>

<style></style>
