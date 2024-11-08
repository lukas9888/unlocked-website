<template>
    <v-sheet
    class="section">
      <v-img
        gradient="to bottom, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 1)"
      src="../assets/Lukas.jpg">
        <v-container>
          <h1>About me</h1>
          <p
          class="pb-4">
            I am a product owner with a developer mindset and a passion for creating beautiful and functional web applications.
            I have experience with a wide range of technologies, including Vue.js, Typescript, Python, and PostgreSQL.
            I am always looking for new challenges and opportunities to learn and grow.
          </p>
          <CTAButton
          class="pa-4">
          </CTAButton>
        </v-container>
      </v-img>
    </v-sheet>
</template>


<script setup lang="ts">
</script>


<style scoped>
.section {
  background-color: black;
  min-height:100vh;
}
</style>
