<script setup lang="ts">
</script>
<template>
  <v-container class="text-center">
    <v-row justify="center">
      <v-col cols="12" md="4" sm="6" >
        <router-link to="/inicio" class="link">
        <v-btn rounded="xl" size="x-large" block class="btn">
          Empezar
        </v-btn>
        </router-link>
      </v-col>
    </v-row>
  </v-container>
</template>
<style scoped>
.link{
  text-decoration: none;
}
</style>