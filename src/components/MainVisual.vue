<script setup lang="ts">
import img from "../assets/image/main.png";
import main_title from "../assets/image/main_title.png";

const props = defineProps({
  type: String,
});
</script>

<template>
  <div :class="['main_visual', props.type]">
    <img :src="img" class="main" />
    <img :src="main_title" class="main_title" />
  </div>
</template>

<style scoped>
.main_visual {
  position: relative;
  font-family: "Nanum Myeongjo", serif;
  text-align: center;
  color: var(--vt-c-white);
  min-height: 500px;
}

.main_visual .main {
  width: auto;
  min-height: 500px;
  max-height: 98vh;
  transform: translateX(-50%);
  margin-left: 50%;
}

.main_visual .main_title {
  width: 252px;
  height: 144px;
  position: absolute;
  left: 0;
  right: 0;
  top: 50px;
  margin: 0 auto;
}
.titles {
  position: absolute;
  top: 100px;
  left: 30px;
  right: 30px;
  text-align: center;

  font-size: 30px;
  font-weight: bolder;
  line-height: 50px;
  letter-spacing: 3px;
}

.subtitle {
  margin-bottom: 20px;
  font-size: 20px;
}

.bottom {
  position: absolute;
  bottom: 30px;
  font-size: 20px;
  width: 100%;
}

@media (min-width: var(--breakpoint)) {
}
</style>
