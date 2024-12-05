<template>
  <v-card class="mx-auto" :width="width" :prepend-icon="icon">
    <!-- Título -->
    <template v-slot:title>
      <span class="font-weight-black">{{ title }}</span>
    </template>

    <!-- Subtítulo -->
    <v-card-subtitle v-if="subtitle">
      {{ subtitle }}
    </v-card-subtitle>

    <!-- Contenido -->
    <v-card-text class="bg-surface-light pt-4">
      {{ content }}
    </v-card-text>

    <!-- Enlace al Artículo -->
    <v-card-actions v-if="articleLink">
      <v-btn :href="articleLink" target="_blank" color="primary" text>
        Leer más
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true, // Título principal
  },
  subtitle: {
    type: String,
    default: "", // Subtítulo (opcional)
  },
  content: {
    type: String,
    required: true, // Texto del contenido
  },
  icon: {
    type: String,
    default: "", // Ícono opcional para prepend-icon
  },
  width: {
    type: String,
    default: "400", // Ancho de la tarjeta
  },
  articleLink: {
    type: String,
    default: "", // URL del enlace al artículo
  },
});
</script>

<style scoped>
.font-weight-black {
  font-weight: 900;
}
</style>
