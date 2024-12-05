<script setup lang="ts">

import Articles from "~/components/material/Articles.vue";
import Videos from "~/components/material/Videos.vue";
</script>

<template>
  <main>
    <HeroAll
        title="Descrube más recursos sobre el Agua"
        :breadcrumbs="[
          { label: 'Inicio', link: '/inicio' },
          { label: 'Materiales', link: '/material' },
          { label: 'Recursos' } // Este no tiene enlace
    ]"
    />
    <Articles/>
    <Videos/>
  </main>
</template>

<style scoped>

</style>