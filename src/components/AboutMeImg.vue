<template>
  <div class="container">
    <div class="scrolling"
         :class="scrollingClass">
      <div class="bg">
        <img src="../assets/Lukas.jpg" alt="Background Image">
      </div>
      <div class="about">
        <div class="about-content">
          <h1>About me</h1>
          <p>
            I am a product owner with a developer mindset and a passion for creating beautiful and functional web applications.
            I have experience with a wide range of technologies, including Vue.js, Typescript, Python, and PostgreSQL.
            I am always looking for new challenges and opportunities to learn and grow.
          </p>
        </div>
      </div>
    </div>
    <ul class="scroll-wrap">
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const scrollingClass = ref('scrolling step-1');

function handleScroll() {
  const winTop = window.scrollY || document.documentElement.scrollTop;
  const winHeight = window.innerHeight;
  const winMid = winHeight / 2 + winTop;
  const winBot = winHeight + winTop;

  const listItems = document.querySelectorAll('.scroll-wrap li');
  let inViewIndex = 0;

  listItems.forEach((li, index) => {
    const rect = li.getBoundingClientRect();
    const liTop = rect.top + winTop;
    const liBot = liTop + rect.height;

    if (liBot <= winMid || liTop >= winBot) {
      li.classList.remove('inView');
    } else if (liTop <= winMid) {
      li.classList.add('inView');
      inViewIndex = index + 1;
    } else {
      li.classList.remove('inView');
    }
  });

  scrollingClass.value = `scrolling step-${inViewIndex || 1}`;
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.container {
  margin: 0;
  padding: 0;
}

ul,
li {
  margin: 0;
  padding: 0;
  list-style: none;
}

.scroll-wrap {
  position: relative;
}

.scroll-wrap li {
  height: 100vh;
}

.scrolling {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  color: #fff;
  background: black;
}

.scrolling .bg {
  width: 100vw;
  height: 120vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.scrolling .bg img {
  width: 100%;
  height: auto;
  transition: 1s;
}

.about {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  text-align: center;
  opacity: 0;
  transition: opacity 1s;
}

.about-content {
  display: inline-block;
  text-align: left;
  margin-top: 20%;
  width: 50%;
  color: white;
  transform: scale(2);
  transition: transform 1s;
}

.scrolling.step-2 .about {
  opacity: 1;
}

.scrolling.step-2 .about-content {
  transform: scale(1);
}

.scrolling.step-3 .about-content {
  transform: scale(0.5);
}
</style>
