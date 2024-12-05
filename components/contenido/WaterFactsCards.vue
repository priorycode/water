<script setup lang="ts">
import Card from "~/components/contenido/Card.vue";
</script>

<template>
  <section class="container-general">
    <article class="container">
      <div class="container-section1">
        <h2>Datos Curiosos sobre el Agua</h2>
        <div class="container-cards">
          <Card
              title="El Agua y los Océanos"
              subtitle="El corazón del clima global"
              imageSrc="https://cdn.pixabay.com/photo/2018/06/13/18/20/waves-3473335_1280.jpg"
              expandableText="Los océanos cubren el 71% de la superficie terrestre y almacenan más del 90% del calor adicional causado por el cambio climático, estabilizando las temperaturas globales."
              buttonText="Leer más"
              buttonColor="blue-lighten-2"
              buttonLink="https://es.wikipedia.org/wiki/Mar"
          />
          <Card
              title="El Agua Dulce"
              subtitle="Un recurso limitado"
              imageSrc="https://cdn.slidesharecdn.com/ss_thumbnails/1aguadulceyaguasalada-130114122108-phpapp01-thumbnail.jpg?width=640&height=640&fit=bounds"
              expandableText="Solo el 2.5% del agua en la Tierra es dulce, y menos del 1% está disponible para el consumo humano. Es un recurso esencial pero extremadamente escaso."
              buttonText="Leer más"
              buttonColor="green-lighten-2"
              buttonLink="https://es.wikipedia.org/wiki/Agua_dulce"
          ></Card>

          <Card
              title="El Ciclo del Agua"
              subtitle="Renovación constante"
              imageSrc="https://concepto.de/wp-content/uploads/2023/10/importancia-del-ciclo-del-agua-1.jpg"
              expandableText="El agua que bebemos hoy podría haber sido parte de un río hace millones de años. El ciclo del agua recicla constantemente este recurso vital en la naturaleza."
              buttonText="Leer más"
              buttonColor="cyan-lighten-2"
              buttonLink="https://es.wikipedia.org/wiki/Ciclo_del_agua"
          ></Card>
        </div>
      </div>
    </article>
  </section>

</template>

<style scoped>
.container-general{
  background: #E9F9FF;
}
.container-section1 {

  display: flex;
  flex-direction: column;
  gap: 30px;
  align-items: center;
  padding: 99px 0;
}

img {
  height: 350px;
}

h2 {
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 40px;
  max-width: 400px;
  margin-bottom: 15px;
  text-align: center;
}

.container-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 1fr; /* Establece que todas las filas tengan la misma altura */
  gap: 20px; /* Espacio entre tarjetas */
}

.container-cards > * {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%; /* Asegura que todas las tarjetas ocupen el mismo espacio */
}
</style>
