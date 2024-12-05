<script setup lang="ts">

import ListaCreditos from "~/components/creditos/ListaCreditos.vue";
</script>

<template>
  <main>
      <HeroAll
          title="Responsables de que esta web exista"
          :breadcrumbs="[
            { label: 'Inicio', link: '/inicio' },
            { label: 'Creditos', link: '/creditos' },
            { label: 'Involucrados' } // Este no tiene enlace
          ]"
      />
    <ListaCreditos
    />
  </main>
</template>

<style scoped>

</style>