<script setup lang="ts">

import Quiz from "~/components/evaluacion/Quiz.vue";
</script>

<template>
  <main>
    <HeroAll
        title="Evalúa tu Conocimiento sobre el Agua"
        :breadcrumbs="[
            { label: 'Inicio', link: '/inicio' },
            { label: 'Evaluacion', link: '/evaluacion' },
            { label: 'Evalúate' } // Este no tiene enlace
          ]"
    />
    <Quiz/>
  </main>
</template>

<style scoped>

</style>