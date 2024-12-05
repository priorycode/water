<script setup lang="ts">

</script>

<template>
  <section class="container-hero">
    <!-- Fondo de video -->
    <video autoplay loop muted playsinline class="background-video">
      <source src="../../assets/video/water2.mp4" type="video/mp4" />
      Tu navegador no soporta videos en HTML5.
    </video>

    <!-- Contenido del Hero -->
    <article class="hero">
      <h1>Explora el Fascinante Mundo del Agua</h1>
      <p class="poppins-regular">Desde su composición química hasta su impacto en la evolución de las civilizaciones, el agua es la base de la vida y del progreso. Descubre su importancia desde diferentes perspectivas.</p>
      <div class="container-btn">
        <a href="#chemistry">
        <v-btn class="btn" rounded="xl" size="x-large" variant="outlined" block>Comienza a explorar</v-btn>
        </a>
      </div>
    </article>
  </section>
</template>

<style scoped>
.container-hero {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: calc(100vh - 150px);
  overflow: hidden;
  background: rgba(10, 151, 202, 0.80);
}

.background-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}

.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
  max-width: 1200px;
  color: white;
  z-index: 1;
  text-align: center;
}

h1 {
  text-shadow: 0px 4px 10px rgba(0, 0, 0, 0.50);
  font-size: 68px;
  font-style: normal;
  font-weight: 700;
  line-height: 90px;
}

p {
  text-shadow: 0px 4px 10px rgba(0, 0, 0, 0.50);
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  max-width: 800px;
  margin-bottom: 10px;
}

.container-btn {
  width: fit-content;
}
.container-btn a{
  text-decoration: none;
  color: white;
}
.btn{
  color: white;
  transition: all .2s ease-in-out;
}
.btn:hover{
  scale: 1.1;
  background: #00ADED;
}
</style>
