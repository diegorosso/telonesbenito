<template>
  <section class="section testi text-center" aria-label="testimonials">
    <h2 class="headline-1 section-title">Reseña de Google</h2>
    <div class="container">
      <p
        class="headline-2 otrafuente testi-text"
        :class="{ visible: currentTestimonial }"
      >
        {{ currentTestimonial }}
      </p>

      <div class="wrapper">
        <div class="separator"></div>
        <div class="separator"></div>
        <div class="separator"></div>
      </div>

      <div class="stars">
        <ion-icon name="star"></ion-icon>
        <ion-icon name="star"></ion-icon>
        <ion-icon name="star"></ion-icon>
        <ion-icon name="star"></ion-icon>
        <ion-icon name="star"></ion-icon>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      testimonials: [
        "Excelentes trabajos y terminaciones. Primero: se trata de una excelente persona y profesional que conoce mucho del tema. Segundo: se ocupa de que sus trabajos queden excelentes. Tercero: el trato es muy bueno. No pensaría jamás en otro lugar para hacer éstos trabajos. Silla Star Trek",
        "El trabajo que hicieron en @delatia.espacio fue espectacular! Estoy muy agradecido con Julio y toda su familia. Es completamente recomendable, da gusto trabajar con personas como ellos. 👏👏👏👏👏",
        "Excelente producto y atención. Superó expectativas! Súper recomiendo.",
        "Atención personalizada. Excelente equipo de trabajo. Muy buen gusto. El cortinado nace desde el techo, un detalle especial. Son unos dias y el resultado es excelente. Muy prolija la colocación.",
        "Excelente atencion. Trabajos profesionales y de muy buena calidad.",
      ],
      currentTestimonial: "", // Texto del comentario actual
      testimonialIndex: 0, // Índice del comentario actual
    };
  },
  mounted() {
    this.startTestimonials();
  },
  methods: {
    startTestimonials() {
      this.currentTestimonial = this.testimonials[this.testimonialIndex];

      // Cambiar el comentario cada 5 segundos con animación
      setInterval(() => {
        this.testimonialIndex =
          (this.testimonialIndex + 1) % this.testimonials.length;
        this.currentTestimonial = this.testimonials[this.testimonialIndex];
      }, 5000); // Cambia cada 5 segundos
    },
  },
};
</script>

<style scoped>
.headline-1 {
  margin-bottom: 3rem;
}

.otrafuente {
  font-size: var(--fontSize-body-1);
}

.section {
  position: relative;
  background-image: url("@/assets/imagenes/TELONES NEGROS-33.webp");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.testi .quote {
  font-size: 7rem;
  font-family: var(--fontFamily-forum);
  line-height: 0.7em;
}

.testi .wrapper {
  display: flex;
  justify-content: center;
  gap: 2px;
  margin-block: 40px 50px;
}

.testi .separator {
  animation: rotate360 15s linear infinite;
}

.testi .testimonial-note {
  font-size: 1.2rem;
  font-weight: bold;
  color: #fff;
  margin-top: 20px;
  opacity: 0.7;
}

.profile .img {
  margin-inline: auto;
  border-radius: var(--radius-circle);
  margin-block-end: 15px;
}

.testi .profile-name {
  color: var(--gold-crayola);
  font-weight: var(--weight-bold);
  text-transform: uppercase;
  letter-spacing: var(--letterSpacing-3);
}

.stars {
  display: flex;
  justify-content: center;
  gap: 5px;
  margin-top: 20px;
}

.stars ion-icon {
  color: #ffd700; 
  font-size: 2.5rem; 
}

.testi-text {
    opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
  min-height: 100px; 
  display: flex; 
  align-items: center; 
  justify-content: center; 
  text-align: center; 
}

.testi-text.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Animación de rotación */
@keyframes rotate360 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
