<script setup lang="ts">
import { ref } from "vue";
import { MenuIcon, XIcon } from "lucide-vue-next";

const menuOpen = ref(false);

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value;
};

const closeMenu = () => {
  if (menuOpen.value) {
    menuOpen.value = false;
  }
};
</script>

<template>
  <div class="container" @click.self="closeMenu">
    <header class="header">
      <router-link to="/" class="logo" >
        <img src="@/public/gota_blue.svg" class="icon" />
        <span>water world</span>
      </router-link>
      <nav :class="['navbar', { open: menuOpen }]" @click.self="closeMenu" >
        <router-link to="/inicio" @click.self="closeMenu">Contenido</router-link>
        <router-link to="/activity" @click.self="closeMenu">Actividades</router-link>
        <router-link to="/material" @click.self="closeMenu">Material Complementario</router-link>
        <router-link to="/evaluacion" @click.self="closeMenu">Evaluacion</router-link>
        <router-link to="/creditos" @click.self="closeMenu">Créditos</router-link>
      </nav>
      <div class="icon-bar" @click="toggleMenu">
        <MenuIcon v-if="!menuOpen" />
        <XIcon v-else />
      </div>
    </header>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  background-color: #fff;
  color: #485194;
  position: relative;
  height: 80px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  text-decoration: none;
  font-size: 22px;
  transition: all .2s ease-in-out;
}

.logo:hover{
  scale: 1.12;
}

.logo img {
  height: 32px;
  width: auto;
}

.navbar {
  display: flex;
  gap: 30px;
}

.navbar a {
  color: #2c3e50;
  text-decoration: none;
  font-weight: 500;
  font-size: 18px;
  transition: all .2s ease-in-out;
}

.navbar a:hover {
  color: #00ADED;
  scale: 1.12;
}

.icon-bar {
  display: none;
  cursor: pointer;
}

.icon-bar svg {
  width: 24px;
  height: 24px;
  color: #485194;
}

/* Responsivo */
@media (max-width: 768px) {
  .navbar {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #fff;
    flex-direction: column;
    justify-content: center;
    gap: 10px;
    padding: 10px 0;
    display: none;
    text-align: center;
  }

  .navbar.open {
    display: flex;
    z-index: 20;
  }
  .navbar a {
    padding: 15px 0;
    width: 100%;
  }
  .icon-bar {
    display: block;
  }
}
</style>