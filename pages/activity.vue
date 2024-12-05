<script setup lang="ts">
import Juegos from "~/components/activity/Juegos.vue";
</script>
<template>
    <main>
      <HeroAll
          title="Descubre el Poder del Agua Jugando"
          :breadcrumbs="[
            { label: 'Inicio', link: '/inicio' },
            { label: 'Actividades', link: '/activity' },
            { label: 'Juegos Interactivos' } // Este no tiene enlace
          ]"
      />
      <Juegos/>
    </main>
</template>

<style scoped>

</style>