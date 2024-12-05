<template>
  <footer class="footer">
    <section class="container footer-container">
      <div class="logo-container">
        <img src="~/public/gota_blue.svg">
        <h3>Water World</h3>
        <p>bibendum honestatis curabitur cu pro veniam doctus evertitur definitionem iisque vituperata omnesque dictumst sociosqu lacinia eros accommodare vitae eirmod eripuit</p>
      </div>
      <nav class="menu">
        <h3>Link de importancia</h3>
        <router-link to="/inicio" class="link">Contenido</router-link>
        <router-link to="/actividades" class="link">Actividades</router-link>
        <router-link to="/material" class="link">Material Complementario</router-link>
        <router-link to="/creditos" class="link">Créditos</router-link>
      </nav>
    </section>
    <section class="credito">
        <strong>2024 &copy Hecho por Camilo</strong>
    </section>
  </footer>
</template>
<style scoped>
.footer {


}
.footer-container{
  padding: 78px 0;
  border-bottom: 1px solid #BDBDBD;
  display: flex;
  justify-content: space-between;
}
.logo-container{
  max-width: 400px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.logo-container img{
  width: 100px;
}
.logo-container h3{
  font-size: 22px;
}

.menu{
  display: flex;
  flex-direction: column;
  gap: 20px;

}
.link{
  text-decoration: none;
  color: #2c3e50;
  font-size: 18px;
  transition: all .2s ease-in-out ;
}
.link:hover{
  color: #00ADED;
  scale: 1.12;
}
.credito{
  display: flex;
  justify-content: center;
  padding: 19px 0;
}
</style>