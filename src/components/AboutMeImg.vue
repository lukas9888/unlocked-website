<template>
    <v-img
    class="bgimg"
    src="..\assets\Lukas.jpg"
    cover
    >
    <v-container
      class="content-container"
    >
    <v-card
      class="about-me-card align-center justify-center"
      :class="isCardExpanded ? 'about-me-card-transition' : 'about-me-card'"
      tile
    >
      <v-card-title>
        <h1>About me</h1>
      </v-card-title>
      <v-card-text
      >
        <p>
          I am a product owner with a developer mindset and a passion for creating beautiful and functional web applications.
          I have experience with a wide range of technologies, including Vue.js, Typescript, Python, and PostgreSQL.
          I am always looking for new challenges and opportunities to learn and grow.
        </p>
      </v-card-text>
    </v-card>
      </v-container>
    </v-img>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const isCardExpanded = ref(false);

function handleScroll() {
  const scrollTop = window.scrollY || document.documentElement.scrollTop;
  // Adjust the scroll threshold as needed
  if (scrollTop > 100) {
    isCardExpanded.value = true;
  } else {
    isCardExpanded.value = false;
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.bgimg {
  opacity: 0.8;
  width: 100%;
}
.content-container {
  position: absolute;
  top: -25%;
  left: -25%;
  height: 100%;
  display: flex;
  align-items: center; /* Centers the content vertically */
  justify-content: flex-start; /* Aligns the content to the left */
  padding-left: 20px; /* Add some padding to the left if necessary */
}

 .about-me-card {

   margin: auto;
   opacity: 0.7;
   max-width:500px;
 }

.about-me-card-transition {

  width: 100%;
  height: 100%;
  opacity: 0.6;
  background: black;
}
</style>
