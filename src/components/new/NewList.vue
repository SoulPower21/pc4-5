<template>
  <h5>Listado de Noticias</h5>
  <div class="product-list">
    <div class="product-grid">
      <div class="product-item" v-for="New in News" :key="New.copyright">
        <NewItem :New="New" />
      </div>
    </div>
  </div>
</template>
<style>
.product-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 50px;
}
</style>

<script>
import axios from "axios";
import NewItem from "src/components/new/NewItem.vue";

export default {
  name: "NewList",
  components: {NewItem},
  data() {
    return {
      News: [],
    };
  },

  mounted() {
    this.loadNews();
  },
  methods: {
    loadNews() {
      const URL = `https://api.nasa.gov/planetary/apod?api_key=kDfNKHQf8cuqSpbcq0dhxehSaV6xNKR37xYdhMXk&start_date=2024-05-01&end_date=2024-06-10`;

      axios
        .get(URL)
        .then((response) => {
          this.News = response.data;
          console.log("News loaded: ", this.News);
        })
        .catch((error) => {
          console.log("Ocurrió un error", error);
          this.$router.push("/");
        });
    },
  },
};
</script>
