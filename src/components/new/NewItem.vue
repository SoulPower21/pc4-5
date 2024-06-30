<template>
  <q-card class="news-card">
    <q-card-section>
      <q-img :src="New.url" alt="Imagen de la noticia" />
    </q-card-section>
    <q-card-section>
      <div class="text-h6 font-weight-bold">
        {{ New.title }}
      </div>
      <div class="news-description">{{ New.date }}</div>
      <div class="news-description">{{ New.explanation }}</div>

    </q-card-section>
  </q-card>
</template>

<style>
.news-card {
  width: 100%;
  max-width: 500px;
  margin-bottom: 20px;
  background-color:azure;
}

.news-card q-card-section {
  height: auto;
  overflow: hidden;
}

.news-description {
  font-size: 14px;
  line-height: 1.5;
  color: #333;
}
</style>


<script>
export default {
  name: "NewsItem",
  props: {
    New: {
      type: Object,
      required: true,
    },
  },
};
</script>
