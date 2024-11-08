<template>
<v-item-group>
  <v-container>
    <h1>Skills</h1>
    <v-row>
      <v-col
        v-for="n in 8"
        :key="n"
        cols="12"
        md="3"
      >
        <v-item v-slot="{ isSelected, selectedClass, toggle }">
          <v-card
            :class="['d-flex align-center', selectedClass]"
            height="200"
            dark
            @click="toggle"
          >
            <div
              class="text-h3 flex-grow-1 text-center"
            >
              skill {{ n }}
            </div>
          </v-card>
        </v-item>
      </v-col>
    </v-row>
  </v-container>

</v-item-group>

</template>

<script setup lang="ts">
import { ref } from 'vue';
let skill = [{id:1, name:"hej"}, {id:2, name:"med"}, {id:3, name:"dig"}];
</script>

<style scoped>
</style>
