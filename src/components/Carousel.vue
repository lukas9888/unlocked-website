<template>
  <v-carousel
    height="400"
    hide-delimiter-background
    cycle
  >
    <template v-slot:prev>
      <v-hover v-slot:default="{ isHovering, props }">
        <v-icon
          v-bind="props"
          :class="['rotate180', isHovering ? 'icon-transition' : '']"
          @click="props.onClick"
        >
          mdi-key
        </v-icon>
      </v-hover>
    </template>

    <template v-slot:next>
      <v-hover v-slot:default="{ isHovering, props }">
        <v-icon
          v-bind="props"
          :class="isHovering ? 'icon-transition' : ''"
          @click="props.onClick"
        >
          mdi-key
        </v-icon>
      </v-hover>
    </template>

    <v-carousel-item
      v-for="(slide, i) in slides"
      :key="i"
    >
      <v-sheet
        :color="colors[i]"
        height="100%"
      >
        <div class="d-flex fill-height justify-center align-center">
          <div class="text-h2">
            {{ slide }} Slide
          </div>
        </div>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script setup lang="ts">
// Script setup here if needed
</script>

<style scoped>
.icon-transition {
  transition: transform 0.7s ease;
  transform: rotateX(180deg);
}
.rotate180 {
  transform: rotateY(180deg);
}
</style>
