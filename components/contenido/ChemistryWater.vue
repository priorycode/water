<script setup lang="ts">

</script>

<template>
  <section class="container" id="chemistry">
    <div class="container-section1">
      <article>
        <h2>El Agua en Términos Químicos</h2>
        <p class="poppins-regular">El agua, compuesta por dos átomos de hidrógeno y uno de oxígeno (H₂O), es una de las moléculas más simples y a la vez fundamentales para la vida. Su polaridad única le permite disolver una amplia variedad de sustancias, haciéndola esencial para procesos químicos en la naturaleza y la industria.</p>
        <div class="container-points">
            <div class="items">
              <img src="@/assets/img/lifewater.png" />
              <h3>Propiedades únicas</h3>
            </div>
          <div class="items">
            <img src="@/assets/img/item2.png" />
            <h3>Ciclo Químico</h3>
          </div>
          <div class="items">
            <img src="@/assets/img/item3.png" />
            <h3>Transporte de Sustancias</h3>
          </div>
        </div>
      </article>
      <img src="@/assets/img/section1.png" />
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