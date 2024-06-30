<template>
  <div class="new-page">
    <div class="new-filter q-ml-md q-mr-xl">
      <NewFilter />
    </div>
    <div class="new-list q-mr-md">
      <NewList />
    </div>
  </div>
</template>

<style>
.new-page {
  display: flex;
  justify-content: space-between;
}

.new-filter {
  width: 25%;
}

.new-list {
  width: 75%;
}
</style>

<script>
import NewFilter from "src/components/new/NewFilter.vue";
import NewList from "src/components/new/NewList.vue";

export default {
  name: "NewsPage",
  components: {
    NewFilter,
    NewList,
  },
};
</script>
