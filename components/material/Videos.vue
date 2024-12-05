<script setup lang="ts">
import { ref } from "vue";
import VideoPopup from "~/components/material/VideoPopup.vue";
import CardVideo from "~/components/material/CardVideo.vue";

// Control del estado del popup
const isPopupVisible = ref(false);
const popupVideoId = ref("");
const popupTitle = ref("");

// Función para abrir el popup con los datos específicos
const openPopup = (videoId: string, title: string) => {
  popupVideoId.value = videoId;
  popupTitle.value = title;
  isPopupVisible.value = true;
};
</script>

<template>
  <section class="container">
    <div class="container-videos">
      <h2>Videos</h2>
      <div class="videos">
        <!-- Card 1: El Ciclo del Agua -->
        <CardVideo
            title="El Ciclo del Agua"
            description="Explora cómo el agua recorre nuestro planeta."
            image="https://img.youtube.com/vi/zcBnm681O5Q/maxresdefault.jpg"
            :onPlay="() => openPopup('zcBnm681O5Q', 'El Ciclo del Agua')"
        />

        <!-- Card 2: La Importancia del Agua -->
        <CardVideo
            title="La Importancia del Agua"
            description="Descubre por qué el agua es un recurso fundamental para la vida."
            image="https://img.youtube.com/vi/m8iuW-qtPBQ/maxresdefault.jpg"
            :onPlay="() => openPopup('m8iuW-qtPBQ', 'La Importancia del Agua')"
        />

        <CardVideo
            title="Cómo cuidar el agua"
            description="Aprende prácticas sencillas para proteger este recurso vital."
            image="https://img.youtube.com/vi/Wka0KQmCL3w/hqdefault.jpg"
            :onPlay="() => openPopup('Wka0KQmCL3w', 'Cómo cuidar el agua')"
        />


        <!-- Popup del video -->
        <VideoPopup
            v-model="isPopupVisible"
            :videoId="popupVideoId"
            :title="popupTitle"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
.container-videos {
  padding: 50px 0;
}

h2 {
  margin-bottom: 30px;
}

.videos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
</style>
