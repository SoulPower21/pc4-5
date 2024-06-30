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
  width: 100%; /* Ancho del 100% del contenedor */
  max-width: 500px; /* Ancho máximo para controlar el tamaño máximo */
  margin-bottom: 20px; /* Espacio entre las tarjetas */
  background-color:azure;
}

.news-card q-card-section {
  height: auto; /* Altura automática para secciones */
  overflow: hidden; /* Ocultar desbordamiento */
}

.news-description {
  font-size: 14px; /* Tamaño de fuente para la descripción */
  line-height: 1.5; /* Espaciado de línea */
  color: #333; /* Color del texto */
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
