<script setup lang="ts">

import Article from "~/components/material/Article.vue";
</script>

<template>
    <section class="container">
      <div class="container-article">
        <h2 >Artículos</h2>
        <div class="articles">
          <Article
              title="El agua es esencial para la vida"
              subtitle="Descubre su importancia global"
              content="El agua no solo es vital para nuestra supervivencia, sino que también desempeña un papel crucial en la mitigación del cambio climático y el desarrollo sostenible."
              icon=""
              articleLink="https://news.un.org/es/story/2021/03/1489832"
          />
          <Article
              title="El Agua: Un Recurso Vital"
              subtitle="Visión General del Banco Mundial"
              content="El agua es esencial para la vida y el desarrollo sostenible. Descubre cómo el Banco Mundial trabaja para garantizar el acceso a este recurso vital y aborda los desafíos relacionados con el cambio climático y la gestión del agua."
              location="Explora los esfuerzos globales por proteger el agua"
              imageSrc="https://www.bancomundial.org/content/dam/photos/780x439/2021/march/water.jpg"
              icon=""
              articleLink="https://www.bancomundial.org/es/topic/water/overview"
          />
          <Article
              title="El Agua y los Objetivos Globales"
              subtitle="La Visión de las Naciones Unidas"
              content="El agua es un derecho humano fundamental y clave para alcanzar los Objetivos de Desarrollo Sostenible. Conoce cómo las Naciones Unidas abordan los desafíos globales del agua para garantizar un futuro sostenible."
              location="Descubre cómo la ONU trabaja por el agua en el mundo"
              imageSrc="https://www.un.org/sites/un2.un.org/files/styles/large-banner-image-style-3/public/2021/06/SDG6-main-banner.jpg"
              articleLink="https://www.un.org/es/global-issues/water"
          />
        </div>
      </div>
    </section>
</template>

<style scoped>
.container-article{
  padding: 50px 0;
}
h2{
  margin-bottom: 30px;
}

.articles{
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 20px;
}
@media (max-width: 768px) {
  .container-article{
    padding: 30px 16px;
  }
  .articles{
    grid-template-columns: repeat(1,1fr);
  }
}
</style>