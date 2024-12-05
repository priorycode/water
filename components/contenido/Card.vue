<template>
  <v-card class="mx-auto card" :max-width="maxWidth">
    <!-- Imagen -->
    <v-img :height="imageHeight" :src="imageSrc" cover></v-img>

    <!-- Contenido -->
    <v-card-title>
      {{ title }}
    </v-card-title>
    <v-card-subtitle>
      {{ subtitle }}
    </v-card-subtitle>

    <!-- Acciones -->
    <v-card-actions>
      <v-btn :color="buttonColor" text :href="buttonLink" target="_blank">
        {{ buttonText }}
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn
          text
          @click="show = !show"
          class="arrow-btn"
      >
        <template v-if="show">
          <CircleChevronUp class="arrow-icon" />
        </template>
        <template v-else>
          <CircleChevronDown class="arrow-icon" />
        </template>
      </v-btn>
    </v-card-actions>

    <!-- Texto Expandible -->
    <v-expand-transition>
      <div v-show="show" class="expandable-content">
        <v-divider></v-divider>
        <v-card-text>
          {{ expandableText }}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script setup>
import { CircleChevronUp, CircleChevronDown } from "lucide-vue-next"; // Asegúrate de tener lucide-vue-next instalado
</script>

<script>
export default {
  name: "Card",
  props: {
    title: String,
    subtitle: String,
    imageSrc: String,
    expandableText: String,
    buttonText: String,
    buttonColor: String,
    buttonLink: String,
    maxWidth: {
      type: String,
      default: "344px", // Fijo el ancho de la card
    },
    imageHeight: {
      type: String,
      default: "200px",
    },
  },
  data: () => ({
    show: false,
  }),
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 344px; /* Fija el ancho para que sea consistente */
  height: auto; /* Permite que la altura se ajuste según el contenido */
}

.arrow-icon {
  color: #485194; /* Cambia el color de los íconos */
  font-size: 24px; /* Ajusta el tamaño del icono */
}

.expandable-content {
  padding: 16px;
}
</style>
