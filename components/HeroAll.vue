<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true, // Título principal del hero
  },
  breadcrumbs: {
    type: Array,
    required: true, // Lista de objetos para los breadcrumbs
  },
});
</script>

<template>
  <section class="container-hero">
    <div class="container hero-container">
      <!-- Título Principal -->
      <div class="container-title">
        <h1>{{ title }}</h1>
      </div>

      <!-- Breadcrumbs -->
      <strong>
        <template v-for="(breadcrumb, index) in breadcrumbs" :key="index">
          <!-- Si el breadcrumb tiene enlace -->
          <router-link
              v-if="breadcrumb.link"
              class="link"
              :to="breadcrumb.link"
          >
            {{ breadcrumb.label }}
          </router-link>
          <!-- Si es el último breadcrumb (sin enlace) -->
          <span v-else>
            {{ breadcrumb.label }}
          </span>
          <!-- Separador, excepto para el último elemento -->
          <span v-if="index < breadcrumbs.length - 1"> > </span>
        </template>
      </strong>
    </div>
  </section>
</template>

<style scoped>
.container-hero {
  height: 360px;
  background: linear-gradient(180deg, #0A97CA 0%, #00ADED 100%);
  color: white;
  display: flex;
  align-items: center;
}


.container-title {
  max-width: 1000px;
  margin-bottom: 30px;
}

h1 {
  font-size: 60px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}



strong .link {
  color: white;
  transition: color 0.2s ease-in-out;
}

@media (max-width: 768px) {
  .container-hero {
    padding: 10px 16px;
  }
  h1{
    font-size: 45px;
  }
  strong .link {
    font-size: 14px;
  }
}

strong .link:hover {
  color: #2c3e50;
}
</style>
