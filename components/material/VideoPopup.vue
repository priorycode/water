<template>
  <v-dialog v-model="isVisible" max-width="800px" persistent>
    <v-card>
      <!-- Header del Popup -->
      <v-card-title class="d-flex justify-space-between align-center">
        <span>{{ title }}</span>
        <v-btn icon @click="close">
          <X />
        </v-btn>
      </v-card-title>

      <!-- Contenido del Popup con iframe -->
      <v-card-text>
        <iframe
            :src="videoUrl"
            frameborder="0"
            width="100%"
            height="450"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
        ></iframe>
      </v-card-text>

      <!-- Footer del Popup (Opcional) -->
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary" text @click="close">Cerrar</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script setup lang="ts">
import { ref, watch, defineProps, defineEmits } from "vue";
import {X} from 'lucide-vue-next'
// Definir las props que recibirá el componente
const props = defineProps({
  videoId: {
    type: String,
    required: true, // ID del video de YouTube
  },
  title: {
    type: String,
    default: "Video", // Título del popup
  },
  modelValue: {
    type: Boolean,
    default: false, // Controla la visibilidad del popup
  },
});

// Emitir eventos
const emit = defineEmits(["update:modelValue"]);

// Estado interno para controlar la visibilidad del popup
const isVisible = ref(props.modelValue);

// Generar la URL del video de YouTube
const videoUrl = computed(() => `https://www.youtube.com/embed/${props.videoId}`);

// Observar cambios en la prop modelValue para sincronizar la visibilidad
watch(
    () => props.modelValue,
    (newVal) => {
      isVisible.value = newVal;
    }
);

// Emitir cambios cuando la visibilidad cambie
watch(isVisible, (newVal) => {
  emit("update:modelValue", newVal);
});

// Función para cerrar el popup
const close = () => {
  isVisible.value = false;
};
</script>

<style scoped>
iframe {
  border-radius: 8px;
}
</style>
