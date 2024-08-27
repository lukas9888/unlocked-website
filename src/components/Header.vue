<template>
 <v-footer class="bg-black">
   <v-row justify="center" no-gutters>
     <v-btn
       v-for="link in links"
       :key="link"
       class="mx-2 secondary-btn"
       color="white"
       rounded="xl"
       variant="text"
     >
       {{ link }}
     </v-btn>
   </v-row>
 </v-footer>
</template>

<script setup lang="ts">
  const links = [
    'About me',
    'Projects',
    'Contact',
  ]

</script>

<style scoped>
.secondary-btn:hover {
  color: #02CFAA !important;
}
</style>
