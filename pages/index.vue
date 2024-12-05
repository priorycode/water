<script setup lang="ts">
import ButtonInicio from "~/components/buttonInicio.vue";
definePageMeta({
  layout: 'none',
})
</script>
<template>
  <section class="inicio">
    <div class="super">
      <div class="container-welcome">
        <img src="@/public/icon.svg" class="img-icon" />
        <h1>Bienvenidos a "El Mundo del Agua"</h1>
        <p>Explora el papel vital del agua en la vida, la ciencia y la historia.</p>
        <ButtonInicio/>
      </div>
    </div>
  </section>
</template>
<style scoped>
.inicio {
  background: #5DCCFC;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.container-welcome {
  width: 90%;
  max-width: 500px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 15px;
}

.img-icon {
  width: 30vw;
  max-width: 150px;
}

@media (max-width: 768px) {
  .container-welcome {
    width: 100%;
    max-width: none;
  }
}


</style>