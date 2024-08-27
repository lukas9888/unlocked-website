<template>
  <v-hover v-slot:default="{ isHovering, props }">
    <v-btn
      v-bind="props"
      class="mx-auto primary-btn"

    >
      Contact
      <v-icon
        class="ml-2"
        :class="isHovering ? 'icon-transition' : ''"
      >
        {{ isHovering ? 'mdi-lock-open-variant' : 'mdi-lock' }}
      </v-icon>
    </v-btn>
  </v-hover>
</template>

<style scoped>
.icon-transition {
  transition: transform 0.3s ease;
  transform: rotate(360deg);
}
.primary-btn {
  border-radius: 25px;
  background-color: #02CFAA;
  color: black;
}
</style>
