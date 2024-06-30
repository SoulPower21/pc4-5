<template>
  <div>
    <h6>Filtros</h6>
    <div class="filtro-fecha">
      <label>Fecha inicial:</label>
      <q-input v-model="startDate" filled type="date" />
    </div>
    <div class="filtro-fecha">
      <label>Fecha final:</label>
      <q-input v-model="endDate" filled type="date" />
    </div>
    <q-btn color="primary" label="Aplicar filtro" @click="applyFilter" />
  </div>
</template>

<script>
export default {
  name: "NewFilter",
  data() {
    return {
      startDate: null,
      endDate: null,
    };
  },
  methods: {
    applyFilter() {
      this.$emit("update-filters", {
        startDate: this.startDate,
        endDate: this.endDate,
      });
    },
  },
};
</script>

<style scoped>
.filtro-fecha {
  margin-bottom: 10px;
}
</style>
