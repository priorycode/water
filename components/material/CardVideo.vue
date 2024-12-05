<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true, // Título del video
  },
  description: {
    type: String,
    required: true, // Descripción del video
  },
  image: {
    type: String,
    required: true, // URL de la imagen del video
  },
  onPlay: {
    type: Function,
    required: true, // Acción al hacer clic en "Ver Video"
  },
});
</script>
<template>
  <v-card class="mx-auto full-width-height">
    <!-- Imagen del video -->
    <v-img :src="image" height="200px" cover></v-img>

    <!-- Contenido -->
    <v-card-title>{{ title }}</v-card-title>
    <v-card-text>{{ description }}</v-card-text>

    <!-- Botón de reproducción -->
    <v-card-actions>
      <v-btn color="primary" text @click="onPlay">
        <v-icon left>mdi-play-circle</v-icon>
        Ver Video
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<style scoped>
.full-width-height {
  width: 100%;
  height: 100%;
}
</style>
