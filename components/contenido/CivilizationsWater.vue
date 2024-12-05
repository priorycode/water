<script setup lang="ts">

</script>

<template>
  <section class="container">
    <div class="container-section1">
      <article>
        <h2>El Agua y las Civilizaciones</h2>
        <p class="poppins-regular">Desde los albores de la humanidad, el agua ha sido el núcleo del desarrollo de las civilizaciones. Los grandes ríos como el Nilo, el Tigris y el Éufrates dieron vida a culturas prósperas, mientras que los acueductos y canales transformaron las ciudades antiguas en centros de innovación y comercio.</p>
        <p class="poppins-regular">El agua impulsó la expansión de las civilizaciones, siendo esencial para la agricultura, navegación y vida cotidiana. Su gestión dio lugar a sistemas de irrigación y almacenamiento para superar retos climáticos y asegurar el crecimiento.</p>
      </article>
      <img src="@/assets/img/section3.png" />
    </div>
  </section>
</template>

<style scoped>
.container-section1{
  display: flex;
  gap: 145px;
  align-items: center;
  padding: 99px 0;
}
img{
  height: 350px;
}
h2{
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 40px;
  max-width: 400px;
  margin-bottom: 15px;
}
p{
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 30px;
  margin-bottom: 15px;
}
.container-points{
  display: flex;
  justify-content: space-between;
  gap: 20px;
}
.items{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}
.items h3{
  max-width: 130px;
  text-align: center;
}
.items img{
  width: 60px;
  height: 60px;
}

</style>