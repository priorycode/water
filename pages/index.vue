<script setup lang="ts">
import ButtonInicio from "~/components/buttonInicio.vue";
 definePageMeta({
   layout: 'none',
 })
</script>
<template>
    <div class="container">
        <div class="container-welcome">
          <img src="@/public/icon.svg" class="img-icon" />
          <h1>Bienvenidos a "El Mundo del Agua"</h1>
          <p>Explora el papel vital del agua en la vida, la ciencia y la historia.</p>
          <ButtonInicio/>
        </div>
    </div>
</template>
<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #5DCCFC;
  }
  .container-welcome {
    width: 500px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    gap: 15px;
  }
  .img-icon{
    width: 150px;
  }
</style>
