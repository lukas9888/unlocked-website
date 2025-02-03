<template>
 <v-footer class="bg-black">
   <v-row justify="center" no-gutters>
     <v-btn
       v-for="link in links"
       :key="link.name"
       :href="link.href"
       class="mx-2 secondary-btn"
       color="white"
       rounded="xl"
       variant="text"
     >
       {{ link.name }}
     </v-btn>
   </v-row>
 </v-footer>
</template>

<script setup lang="ts">
  const links = [
    {name:'About me', href:'#about-me'},
    {name:'Skills', href:'#skills'},
    {name:'Projects', href:'#projects'},
    {name:'Contact', href:'#contact'}
  ]

</script>

<style scoped>
.secondary-btn:hover {
  color: #02CFAA !important;
}
</style>
