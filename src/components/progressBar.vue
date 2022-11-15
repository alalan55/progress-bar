<script setup>
import { ref } from "vue";

const size = ref(0);
const hasMessage = ref(true);
const message = ref("HELLO MY FRIEND");
const mainColor = ref("#4caf50");
const interval = ref(null);

const x = () => {
  size.value++;

  if (size.value == 100) {
    stop();
    console.log("entrei no método");
  }
};

const start = () => (interval.value = setInterval(x, 10));
const stop = () => clearInterval(interval.value);
</script>

<template>
  <div class="wrapper">
    <div class="wrapper__progress">
      <div
        class="wrapper__progress__bg"
        :style="{ width: `${size}%`, backgroundColor: mainColor }"
      ></div>
    </div>
    <div v-if="hasMessage" class="wrapper__message">
      <span :style="{ color: mainColor }">{{ message }}</span>
    </div>
  </div>
  <button @click="start">iniciar</button>
  <button @click="stop">parar</button>
</template>

<style lang="scss" scoped>
.wrapper {
  &__progress {
    background: #f1f1f1;
    height: 30px;
    width: 100%;
    border-radius: 15px;
    overflow: hidden;
    &__bg {
      height: 100%;
      transition: 0.5s ease-in;
    }
  }
  &__message {
    margin: 0.5rem 0;
    padding: 0 0.5rem;
    span {
      font-weight: 600;
    }
  }
}
</style>
