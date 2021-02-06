<template>
  <nav>
    <div class="nav-container">
      <p class="logo">{{ logo }}</p>
      <ul class="nav-links">
        <li @click="rise"><a href="#">Home</a></li>
        <li @mouseenter="addCount"><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Pricing</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </nav>
  <div class="j" ref="box" :class="{ rise: toggle }"></div>
</template>

<script>
import { gsap } from "gsap";

export default {
  name: "Nav",
  props: {
    logo: {
      type: String,
    },
  },
  data() {
    return {
      toggle: false,
    };
  },
  methods: {
    rise() {
      return (this.toggle = !this.toggle);
    },
    move() {
      const { box } = this.$refs;
      let tl = gsap.timeline();

      tl.to(box, { duration: 2.5, ease: "power3.inOut", x: 500 });
    },
    addCount(){
      this.$emit('add-count')
    }
  },
  mounted() {
    this.move();
  },
};
</script>

<style lang="scss" src="../css/nav.scss"></style>
