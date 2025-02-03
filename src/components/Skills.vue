<template>
<v-item-group
id="skills">
  <v-container>
    <h1>Skills</h1>
    <v-row>
      <v-col
        v-for="skill in skills"
        :key="skill.id"
        cols="12"
        sm="6"
        md="3"
      >
        <v-item v-slot="{ isSelected, selectedClass, isHovering, toggle }">
          <div class="card-container">
              <v-card class="text-behind">
                <template v-slot:prepend>
                  <a 
                  :href="skill.link" 
                  class="text-decoration-none d-flex align-center text-white"
                  >
                <v-avatar :image="skill.image" rounded="0" class="ma-2"></v-avatar>
              <v-card-title>{{skill.name}}</v-card-title>
              </a>
            </template>
                <v-card-text>More text about {{ skill.name }}</v-card-text>
              </v-card>
          <v-card
            :class="['skill-card', selectedClass, {'selected-card': isSelected}]"
            height="200"
            color="black"
            @click="toggle"
            
          >
              <v-img 
                :src="skill.image"
                height="150"
              />
              <v-icon class="door-handle">mdi-check</v-icon>
          </v-card>
        </div>
        </v-item>
      </v-col>
    </v-row>
  </v-container>

</v-item-group>

</template>

<script setup lang="ts">
import { ref } from 'vue';
const skills = ref([
  {id:1, name:"Supabase", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/supabase/supabase-original.svg",link:"https://supabase.com"},
  {id:2, name:"Vue", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg", link: "https://vuejs.org"},
  {id:3, name:"TypeScript", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg", link: "https://www.typescriptlang.org"},
  {id:4, name:"PostgreSQL", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg", link: "https://www.postgresql.org"},
  {id:5, name:"Python", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg", link: "https://www.python.org"},
  {id:6, name:"CSS", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg", link: "https://developer.mozilla.org/en-US/docs/Web/CSS"},
  {id:7, name:"HTML", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg", link: "https://developer.mozilla.org/en-US/docs/Web/HTML"},
  {id:8, name:"GitHub", type:"technical", image:"https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg", link: "https://github.com"}]);
</script>

<style scoped>
.card-container {
  position: relative;
  width: 100%;
  height: 200px;
}

.text-behind {
  position: absolute;
  width: 100%;
  height: 100%;
  justify-content: center;
  z-index: 0;
  opacity: 1;
}

.skill-card {
  transform-origin: left;
  transition: 
  transform 1.5s ease-in-out,
  opacity 0.5s ease-in-out, 
  border 0s ease-in-out; 
  display: flex;
  align-items: center;
}

.selected-card {
  transform: 
  perspective(600px)
  rotateY(-90deg);
  /* border: 1px solid white; */
  /* opacity:0; */
  transition: 
    transform 1.5s ease-in-out;
    /* opacity 0.5s ease-in-out 1.5s,
    border 0s ease-in-out 1.5s; */
}

/* .skill-card:hover {
  border: 1px solid white;
}  */

.door-handle {
  opacity:0;
  position:absolute;
  right:8%;
  transform: rotate(-135deg);
}
/* .skill-card:hover .door-handle {
  opacity: 1;
}

.selected-card .door-handle {
  opacity: 1;
  transform: rotate(-155deg);
  transition: transform 0.5s ease-out;
} */
</style>
