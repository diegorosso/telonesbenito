
<template>
    <section class="hero text-center" aria-label="home" id="home">
      <ul class="hero-slider">
        <li
          v-for="(item, index) in slides"
          :key="index"
          :class="['slider-item', { active: currentSlidePos === index }]"
        >
          <div class="slider-bg">
            <img :src="item.img" :alt="item.alt" class="img-cover" />
          </div>
  
          <p class="label-2 section-subtitle slider-reveal">{{ item.subtitle }}</p>
          <h1 class="display-1 hero-title slider-reveal">{{ item.title }}</h1>
          <p class="body-2 hero-text slider-reveal">{{ item.text }}</p>
  
          <a href="#" class="btn btn-primary slider-reveal">
            <span class="text text-1">{{ item.buttonText }}</span>
            <span class="text text-2" aria-hidden="true">{{ item.buttonText }}</span>
          </a>
        </li>
      </ul>
  
      <button class="slider-btn prev" aria-label="slide to previous" @click="slidePrev">
        <ion-icon name="chevron-back"></ion-icon>
      </button>
      <button class="slider-btn next" aria-label="slide to next" @click="slideNext">
        <ion-icon name="chevron-forward"></ion-icon>
      </button>
  
      <a href="#" class="hero-btn has-after">
        <img
          src="../assets/imagenes/logolarural2.png"
          width="80"
          height="80"
          alt="booking icon"
        />
      </a>
    </section>
  </template>
  
  <script>
  import telonImg1 from '@/assets/imagenes/TELONES NEGROS-33.webp';
  import telonImg2 from '@/assets/imagenes/TELONES NEGROS-38.webp';
  import telonImg3 from '@/assets/imagenes/TELONES NEGROS-46.webp';
  import telonImg4 from '@/assets/imagenes/TELONES NEGROS-32.webp';


  export default {
    data() {
      return {
        slides: [
          {
            img: telonImg1,
            alt: "Slide 1",
            subtitle: "Tradicional y elegante",
            title: "Alquiler de telones",
            text: "Crea ambientes únicos con nuestros telones de alta calidad.",
            buttonText: "Ver proyectos",
          },
          {
            img: telonImg2,
            alt: "Slide 2",
            subtitle: "Control total de luz",
            title: "Oscurecimiento de espacios",
            text: "Crea ambientes íntimos y profesionales con nuestros telones.",
            buttonText: "Explorar opciones",
          },
          {
            img: telonImg3,
            alt: "Slide 3",
            subtitle: "Espacios funcionales",
            title: "Acondicionamiento",
            text: "Optimizamos tus espacios con telones versátiles y de calidad.",
            buttonText: "Conoce más",
          },
          {
            img: telonImg4,
            alt: "Slide 4",
            subtitle: "Diseño impecable",
            title: "Fondos de escenarios",
            text: "Realza tus eventos con fondos elegantes y personalizados.",
            buttonText: "Descubre más",
          },
        ],
        currentSlidePos: 0,
        autoSlideInterval: null,
      };
    },
    methods: {
      slideNext() {
        this.currentSlidePos =
          this.currentSlidePos >= this.slides.length - 1
            ? 0
            : this.currentSlidePos + 1;
      },
      slidePrev() {
        this.currentSlidePos =
          this.currentSlidePos <= 0
            ? this.slides.length - 1
            : this.currentSlidePos - 1;
      },
      startAutoSlide() {
        this.autoSlideInterval = setInterval(this.slideNext, 7000);
      },
      stopAutoSlide() {
        clearInterval(this.autoSlideInterval);
      },
    },
    mounted() {
      this.startAutoSlide();
    },
    beforeUnmount() {
      this.stopAutoSlide();
    },
  };
  </script>

<style scoped>
.hero .slider-btn {
  display: none;
}

.hero {
  position: relative;
  padding-block: 120px;
  min-height: 100vh;
  overflow: hidden;
  z-index: 1;
}

.hero .slider-item {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  display: grid;
  place-content: center;
  padding-block-start: 100px;
  opacity: 0;
  visibility: hidden;
  transition: var(--transition-3);
  z-index: 1;
}

.hero .slider-item.active {
  opacity: 1;
  visibility: visible;
}

.hero .slider-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: scale(1.15);
  pointer-events: none;
  user-select: none;
  z-index: -1;
}
.hero .slider-bg img {
  filter: brightness(0.3); /* Reduce el brillo al 70% */
}

.hero .slider-item.active .slider-bg {
  animation: smoothScale 7s linear forwards;
}

@keyframes smoothScale {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.15);
  }
}

.hero .section-subtitle::after {
  margin-block: 14px 20px;
}

.hero-text {
  margin-block: 10px 40px;
}

.hero .btn {
  margin-inline: auto;
}

.hero-btn {
  position: absolute;
  bottom: 15px;
  right: 15px;
  z-index: 2;
  width: 110px;
  height: 110px;
  padding: 12px;
  transform: scale(0.6);
}

.hero-btn img {
  margin-inline: auto;
  margin-block-end: 6px;
}

.hero-btn .span {
  color: var(--black);
  font-weight: var(--weight-bold);
  text-transform: uppercase;
  letter-spacing: var(--letterSpacing-1);
  line-height: var(--lineHeight-3);
}

.hero-btn::after {
  inset: 0;
  border: 1px solid var(--gold-crayola);
  animation: rotate360 15s linear infinite;
}

.slider-reveal {
  transform: translateY(30px);
  opacity: 0;
}

.hero .slider-item.active .slider-reveal {
  animation: sliderReveal 1s ease forwards;
}

@keyframes sliderReveal {
  0% {
    transform: translateY(30px);
    opacity: 0;
  }

  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.hero .slider-item.active .section-subtitle {
  animation-delay: 500ms;
}

.hero .slider-item.active .hero-title {
  animation-delay: 1000ms;
}

.hero .slider-item.active .hero-text {
  animation-delay: 1.5s;
}

.hero .slider-item.active .btn {
  animation-delay: 2s;
}

@media (min-width: 768px) {
  .hero .slider-btn {
    display: grid;
    position: absolute;
    z-index: 1;
    color: var(--gold-crayola);
    font-size: 2.4rem;
    border: 1px solid var(--gold-crayola);
    width: 45px;
    height: 45px;
    place-items: center;
    top: 50%;
    transform: translateY(-50%) rotate(45deg);
    transition: var(--transition-1);
  }

  .hero .slider-btn ion-icon {
    transform: rotate(-45deg);
  }

  .hero .slider-btn.prev {
    left: 30px;
  }

  .hero .slider-btn.next {
    right: 30px;
  }

  .hero .slider-btn:is(:hover, :focus-visible) {
    background-color: var(--gold-crayola);
    color: var(--black);
  }
}

@media (min-width: 1200px) {
  .hero {
    height: 880px;
  }

  .hero-btn {
    bottom: 50px;
    right: 50px;
    transform: scale(1);
  }
}
</style>
