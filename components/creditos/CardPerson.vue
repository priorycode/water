<script setup lang="ts">
import { defineProps } from 'vue';

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
</script>

<template>
  <div class="card">
    <img :src="imageSrc" alt="Profile Picture" class="profile-picture" />
    <h3>{{ name }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<style scoped>
.card {
  width: auto;
  padding: 16px;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  background-color: #fff;
  transition: 0.2s all ease-in-out;
}
@media (max-width: 768px) {
  .card {
    padding: 30px 16px;
    width: auto;
  }
}
.card:hover{
  scale: 1.03;
}
.profile-picture {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
}

h3 {
  font-size: 1.5em;
  margin: 8px 0;
}

p {
  font-size: 1em;
  color: #666;
}
</style>
