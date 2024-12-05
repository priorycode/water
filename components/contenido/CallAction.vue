<script setup lang="ts">

</script>

<template>
  <section class="container-callaction">
    <!-- Fondo de video -->
    <video autoplay loop muted playsinline class="background-video">
      <source src="~/assets/video/water.mp4" type="video/mp4" />
      Tu navegador no soporta videos en HTML5.
    </video>

    <article class="container">
      <div class="callaction">
        <h2 class="poppins-regular-italic">
          "El agua es la fuerza motriz de toda la naturaleza. Es el elemento esencial que da vida, moldea paisajes y sostiene ecosistemas. Sin ella, la humanidad no podría haber alcanzado su desarrollo, y el futuro de nuestra civilización depende de cómo cuidemos este recurso vital."
        </h2>
        <small>— Leonardo da Vinci</small>
      </div>
    </article>
  </section>
</template>

<style scoped>
.container-callaction {
  position: relative;
  padding: 50px 0 80px 0;
  overflow: hidden;
  background: rgba(10, 151, 202, 0.60);
  color: white;
  display: flex;
}

.background-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ajusta el video para cubrir todo el fondo */
  z-index: -1; /* Coloca el video detrás del contenido */
}

h2{
  font-size: 25px;
  padding-bottom: 20px;
  max-width: 800px;
}
.callaction {
  position: relative;
  width: 100%;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

@media (max-width: 768px) {
  h2{
    font-size: 20px;
    margin: 0 16px;
  }
}
</style>
