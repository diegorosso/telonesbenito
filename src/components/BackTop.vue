<template>
    <a
      href="#top"
      class="back-top-btn"
      aria-label="back to top"
      v-bind:class="{ active: isScrolled }"
    >
      <ion-icon name="chevron-up" aria-hidden="true"></ion-icon>
    </a>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isScrolled: false, 
      };
    },
    methods: {
      handleScroll() {
        this.isScrolled = window.scrollY > 200;
      },
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener("scroll", this.handleScroll);
    },
  };
  </script>
  
  <style scoped>
  .back-top-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: var(--gold-crayola);
    color: var(--smoky-black-1);
    font-size: 22px;
    width: 50px;
    height: 50px;
    border-radius: var(--radius-circle);
    display: grid;
    place-items: center;
    box-shadow: var(--shadow-1);
    transition: var(--transition-1);
    opacity: 0;
    visibility: hidden;
    z-index: 4;
  }
  
  .back-top-btn:is(:hover, :focus-visible) {
    background-color: var(--white);
    color: var(--gold-crayola);
  }
  
  .back-top-btn.active {
    opacity: 1;
    visibility: visible;
  }
  </style>
  