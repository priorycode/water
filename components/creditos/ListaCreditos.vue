<script setup lang="ts">
import { defineProps, ref } from 'vue';
import CardPerson from "~/components/creditos/CardPerson.vue";
import jose from "~/assets/img/jose.jpeg";
import maria from "~/assets/img/maria.jpg";
import carlos from "~/assets/img/carlos.jpg";

const props = defineProps({
  imageSrc: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
});

const participants = ref([
  { name: "Jhordy Mondragon", description: "Desarrollador", imageSrc: jose },
  { name: "Maria Gonzalez", description: "Diseñadora", imageSrc: maria },
  { name: "Carlos Ramirez", description: "Analista", imageSrc: carlos }
]);
</script>

<template>
  <div class="container-general">
  <section class="container">
    <h2> Participantes </h2>
    <div class="container-card">
      <CardPerson v-for="(participant, index) in participants" :key="index" :description="participant.description" :name="participant.name" :image-src="participant.imageSrc" />
    </div>
  </section>
  </div>
</template>

<style scoped>

.container-general{
  background: #e9f9ff;
}


h3 {
  font-size: 1.5em;
  margin: 8px 0;
}

p {
  font-size: 1em;
  color: #666;
}

.container{
  padding: 90px 0;

}
h2{
  margin-bottom: 30px;
  font-size: 30px;
}
.container-card{
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 30px;
}
@media (max-width: 768px) {
  .container{
    padding: 30px 16px;
    background: #e9f9ff;
  }
  .container-card{

    grid-template-columns: repeat(1,1fr);
    gap: 30px;
  }
}
</style>
