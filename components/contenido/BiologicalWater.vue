<script setup lang="ts">

</script>

<template>
  <section class="container-section">
    <div class="container">
    <div class="container-section1">
      <article>
        <h2>El Agua en Términos Biológicos</h2>
        <p class="poppins-regular">El agua es el componente esencial para la vida. Está presente en cada célula de los organismos vivos, desempeñando un papel fundamental en funciones vitales como la regulación de la temperatura, el transporte de nutrientes y la eliminación de desechos. Sin ella, la vida como la conocemos sería imposible.</p>
        <div class="container-points">
          <div class="items">
            <img src="@/assets/img/hidratacion.png" />
            <h3>Hidratación Vital</h3>
          </div>
          <div class="items">
            <img src="@/assets/img/item2.png" />
            <h3>Transporte de Nutrientes</h3>
          </div>
          <div class="items">
            <img src="@/assets/img/item3.png" />
            <h3>Control térmico</h3>
          </div>
        </div>
      </article>
      <img src="@/assets/img/section2.png" />
    </div>
    </div>
  </section>
</template>

<style scoped>
.container-section{
  background: #E9F9FF;
}
.container-section1{
  display: flex;
  flex-direction: row-reverse;
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