<template>
  <div>
    <!-- ClockComponent -->
    <Clock class="clock" location="TOKYO" :diff="0" />
    <Clock class="clock" location="NY" :diff="-14" />
    <!-- moveCatComponent -->
    <h1 class="bounce animated">An animated element</h1>
    <div class="stage" @click="moveCat">
      <cat1 ref="cat" />
    </div>
    <!-- svgPathComponent -->
    <div class="stage">
      <SvgPath />
    </div>
    <!-- vueAnimationComponent -->
    <div class="stage">
      <VueAnimation />
    </div>
  </div>
</template>

<script>
import cat1 from "@/components/cat1";
import SvgPath from "@/components/SvgPath";
import VueAnimation from "@/components/VueAnimation";
import Clock from "./components/Clock";

export default {
  components: {
    cat1,
    SvgPath,
    VueAnimation,
    Clock,
  },
  methods: {
    moveCat(ev) {
      this.$refs.cat.moveTo(ev.offsetX);
    },
  },
};
</script>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.0.0/animate.min.css");

.body {
  padding: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.stage {
  position: relative;
  width: 100%;
  height: 350px;
  border: 1px solid #aaa;
  background-color: rgb(248, 248, 247);
  overflow: hidden;
}

.clock {
  width: 80%;
  max-width: 500px;
  margin: 30px auto;
}
</style>

<style>
html {
  font-size: 62.5%;
}

body {
  margin: 0;
}

p {
  margin: 0;
}
</style>
