<script setup lang="ts">
import { ref } from 'vue'

const goal = ref<HTMLElement | null>(null)

const onClick = (event: MouseEvent) => {
  const shoot = event.target as HTMLElement;

  if (goal.value?.contains(shoot)) {
    console.log("goal");
  } else {
    console.log("missed");
  }
}
</script>

<template>
  <div class="container" @click="onClick">
    <div class="goal" ref="goal"></div>
  </div>
</template>

<style scoped>
.container {
  position: relative;
  top: 0;
  left: 0;
  width: 1280px;
  height: 731px;
  max-width: 100vw;
  background-image: url("~/public/images/background.png");
  background-size: cover;
  background-position: center;
}

.goal {
  background-color: red;
  position: absolute;
  top: 380px;
  left: 337px;
  height: 300px;
  width: 607px;
}

@media (max-width: 1300px) {
  .container {
    width: 800px;
    height: 550px;
  }

  .goal {
    top: 239px;
    left: 212px;
    height: 186px;
    width: 377px;
  }
}

@media (max-width: 992px) {
  .container {
    width: 600px;
    height: 600px;
  }

  .goal {
    top: 180px;
    left: 160px;
    height: 140px;
    width: 283px;
  }
}

@media (max-width: 768px) {
  .container {
    width: 600px;
    height: 600px;
  }

  .goal {
    top: 40%;
    left: 15%;
    height: 200px;
    width: 400px;
  }
}

@media (max-width: 480px) {
  .container {
    width: 100%;
    height: auto;
  }

  .goal {
    top: 45%;
    left: 10%;
    height: 180px;
    width: 350px;
  }
}
</style>
