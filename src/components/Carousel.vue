<template>
  <v-carousel
    height="400"
    hide-delimiter-background
    cycle
  >
    <template v-slot:prev>
      <v-hover v-slot:default="{ isHovering, props }">
        <v-btn
          size="x-large"
          variant="text"
          v-bind="props"
          height="100%"
          :ripple="false"
        >
        <v-icon
          class="left-icon"
          :class="isHovering ? 'left-icon-transition' : ''"
          @click="props.onClick"
        >
          mdi-key
        </v-icon>
        </v-btn>
      </v-hover>
    </template>

    <template v-slot:next>
      <v-hover v-slot:default="{ isHovering, props }">
        <v-btn
          size="x-large"
          variant="text"
          v-bind="props"
          height="100%"
          :ripple="false"
        >
        <v-icon
          class="right-icon"
          :class="isHovering ? 'right-icon-transition' : ''"
          @click="props.onClick"
        >
          mdi-key
        </v-icon>
        </v-btn>
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

</script>

<style scoped>
.right-icon {
  transform: rotateX(180deg);
  transition: transform 0.7s ease-in-out;
}

.left-icon {
  transform: rotateY(180deg) rotateX(180deg);
  transition: transform 0.7s ease-in-out;
}

.right-icon-transition {
  transform: rotateX(360deg);
  transition: transform 0.7s ease-in-out;
}

.left-icon-transition {
  transform: rotateY(180deg) rotateX(360deg);
  transition: transform 0.7s ease-in-out;
}
</style>
