<template>
  <div>
    <NewFilter @update-filters="updateFilters" />
    <h5>Listado de Noticias</h5>
    <div class="product-list">
      <div class="product-grid">
        <div class="product-item" v-for="newsItem in news" :key="newsItem.copyright">
          <NewItem :newsItem="newsItem" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import NewItem from "src/components/news/NewItem.vue";
import NewFilter from "src/components/news/NewFilter.vue";

export default {
  name: "NewList",
  components: { NewItem, NewFilter },

  data() {
    return {
      news: [],
    };
  },

  methods: {
    updateFilters(filters) {
      this.fetchNews(filters.startDate, filters.endDate);
    },
    fetchNews(startDate, endDate) {
      if (!startDate || !endDate) {
        return; // Evitar solicitudes vacías
      }

      const apiKey = "kDfNKHQf8cuqSpbcq0dhxehSaV6xNKR37xYdhMXk";
      const baseURL = "https://api.nasa.gov/planetary/apod";
      const URL = `${baseURL}?api_key=${apiKey}&start_date=${startDate}&end_date=${endDate}`;

      axios
        .get(URL)
        .then((response) => {
          this.news = response.data;
          console.log("News loaded:", this.news);
        })
        .catch((error) => {
          console.error("Error fetching news:", error);
        });
    },
  },
};
</script>

<style scoped>
.product-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 30px;
}
</style>
