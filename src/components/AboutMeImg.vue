<template>
  <v-hover v-slot="{ isHovering, props }">
    <v-img
    class="bgimg"
    src="..\assets\Lukas.jpg"
    v-bind="props"
    cover
    >
  <v-expand-transition>
    <v-card
      class="v-card--reveal"
      max-width="1200"
      tile
      v-if="isHovering"
    >
      <v-card-title>
        <h1>About me</h1>
      </v-card-title>
      <v-card-text>
        <p>
          I am a product owner with a developer mindset and a passion for creating beautiful and functional web applications.
          I have experience with a wide range of technologies, including Vue.js, Typescript, Python, and PostgreSQL.
          I am always looking for new challenges and opportunities to learn and grow.
        </p>
      </v-card-text>
    </v-card>
  </v-expand-transition>
    </v-img>
  </v-hover>
</template>

<style scoped>
.bgimg {
  opacity: 0.4;
}
.bgimg:hover {
  transition: opacity 1s;
  opacity: 0.9;
}


.bgimg {
  width: 100%;
}

 .v-card--reveal {
   margin: auto;
   align-items: center;
   justify-content: center;
   opacity: .4;
   width: 100%;
 }
</style>
