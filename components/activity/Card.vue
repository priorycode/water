<template>
  <v-card class="mx-auto" :max-width="maxWidth">
    <!-- Imagen -->
    <v-img
        class="align-end text-white image-container"
        :height="imageHeight"
        :src="imageSrc"
        cover
    >
      <!-- Overlay -->
      <div class="overlay"></div>
      <!-- Título -->
      <v-card-title class="title-overlay">{{ title }}</v-card-title>
    </v-img>

    <!-- Subtítulo -->
    <v-card-subtitle class="pt-4">
      {{ subtitle }}
    </v-card-subtitle>

    <!-- Texto -->
    <v-card-text>
      <div>{{ description }}</div>
      <div>{{ location }}</div>
    </v-card-text>

    <!-- Botón -->
    <v-card-actions>
      <v-btn
          :color="buttonColor"
          text
          v-if="buttonLink"
          :href="buttonLink"
          target="_blank"
      >
        {{ buttonText }}
      </v-btn>
      <v-btn
          :color="buttonColor"
          text
          v-else
          @click="onButtonClick"
      >
        {{ buttonText }}
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true, // Título principal de la tarjeta
  },
  subtitle: {
    type: String,
    required: true, // Subtítulo de la tarjeta
  },
  description: {
    type: String,
    required: true, // Descripción principal
  },
  location: {
    type: String,
    required: true, // Ubicación o información adicional
  },
  imageSrc: {
    type: String,
    required: true, // URL de la imagen
  },
  imageHeight: {
    type: String,
    default: "200", // Altura de la imagen
  },
  buttonText: {
    type: String,
    default: "Explore", // Texto del botón
  },
  buttonColor: {
    type: String,
    default: "orange", // Color del botón
  },
  buttonLink: {
    type: String,
    default: "", // URL del enlace del botón (opcional)
  },
  maxWidth: {
    type: String,
    default: "400", // Ancho máximo de la tarjeta
  },
  onButtonClick: {
    type: Function,
    default: () => {}, // Acción al hacer clic en el botón si no hay enlace
  },
});
</script>

<style scoped>
.image-container {
  position: relative; /* Necesario para posicionar el overlay */
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4); /* Color del lienzo (negro con opacidad) */
  z-index: 1; /* Asegura que esté por debajo del texto */
}

.title-overlay {
  position: relative;
  z-index: 2;
  font-weight: bold;
  font-size: 1.5rem;
  font-size: 20px;
}
</style>
