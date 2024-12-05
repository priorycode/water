<script setup lang="ts">
import imgjuego1 from "~/assets/img/juego1.png"
import imgjuego2 from "~/assets/img/juego2.png"
import imgjuego3 from "~/assets/img/juego3.png"
import imgjuego4 from "~/assets/img/juego4.png"
import Card from "~/components/activity/Card.vue";
</script>

<template>
  <div class="container-general">
  <section class="container">
    <h2>Juegos y Simuladores</h2>
    <div class="container-juego">
        <Card
            title="Juego: El Ciclo del Agua"
            subtitle="Aprende mientras juegas"
            description="Pon a prueba tus conocimientos sobre el ciclo del agua con este juego interactivo. Descubre cómo se mueven las gotas de agua en la naturaleza a través de la evaporación, condensación y precipitación."
            location="Desafía tus habilidades y diviértete aprendiendo"
            :imageSrc="imgjuego1"
            buttonText="¡Jugar Ahora!"
            buttonColor="blue"
            buttonLink="https://wordwall.net/es/resource/19646717/el-ciclo-del-agua"
        />
      <Card
          title="Juego: La Contaminación"
          subtitle="Conoce y aprende jugando"
          description="Explora cómo las actividades humanas afectan el agua en este divertido e interactivo juego. Aprende sobre las causas de la contaminación y cómo podemos contribuir a proteger este recurso vital."
          location="¡Únete al desafío y toma conciencia ambiental!"
          :imageSrc="imgjuego2"
          buttonText="¡Jugar Ahora!"
          buttonColor="green"
          buttonLink="https://wordwall.net/es/resource/4129711/contaminaci%C3%B3n-del-agua"
      />
      <Card
          title="Juego: El Agua"
          subtitle="Explora el mundo del agua"
          description="Descubre la importancia del agua a través de este interactivo juego. Aprende sobre su rol en la naturaleza y por qué es esencial para la vida en la Tierra."
          location="¡Diviértete aprendiendo mientras juegas!"
          :imageSrc="imgjuego3"
          buttonText="¡Jugar Ahora!"
          buttonColor="blue"
          buttonLink="https://wordwall.net/es/resource/20600898/ciclo-del-agua/el-agua"
      />
      <Card
          title="Simulador: Cuidemos el Agua"
          subtitle="Explora y aprende con AySA"
          description="Sumérgete en este simulador interactivo para aprender cómo cuidar el agua y hacer un uso responsable de este recurso esencial. Descubre cómo tus acciones pueden marcar la diferencia."
          location="¡Haz clic y comienza tu experiencia educativa!"
          :imageSrc="imgjuego4"
          buttonText="¡Probar Ahora!"
          buttonColor="teal"
          buttonLink="https://aysa.com.ar/culturayeducacion/simulador"
      />
    </div>
  </section>
  </div>
</template>

<style scoped>
.container-general{
  background: #E9F9FF;
}

.container{
  padding: 90px 0;
}

h2{
  text-align: center;
  margin-bottom: 30px;
  text-align: left;
}
  .container-juego{


    display: grid;
    grid-template-columns:repeat(3,1fr);
    gap: 20px;
  }
@media (max-width: 768px) {
  .container{
    padding: 30px 16px;
  }
  .container-juego{
  grid-template-columns: repeat(1,1fr);
  }
}
</style>