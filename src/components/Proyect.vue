<template>
  <section class="special-dish text-center" aria-labelledby="dish-label" id="proyectos">
    <div class="special-dish-banner">
      <video
        src="../assets/imagenes/APERTURA A LA ITALIANA.mp4"
        autoplay
        loop
        muted
        class="video-banner arc-shape"
      >
        Tu navegador no soporta el elemento de video.
      </video>
    </div>

    <div class="special-dish-content bg-black-10">
      <div class="container">
        <p class="section-subtitle label-2">Proyectos realizados</p>

        <h2 class="headline-1 section-title">Telones a medida</h2>

        <p class="section-text">
          Descubre nuestros proyectos más destacados con telones. Cada diseño es
          único y está pensado para adaptarse a tus necesidades específicas,
          garantizando la mejor calidad y presentación.
        </p>

        <a href="#" class="btn btn-primary" @click.prevent="openGallery">
          <span class="text text-1">Abrir Galería</span>
          <span class="text text-2" aria-hidden="true">Abrir Galería</span>
        </a>
      </div>
    </div>

    <!-- Modal de Galería -->
    <div v-if="showGallery" class="modal-overlay">
      <div class="modal-content">
        <button class="close-btn" @click="closeGallery">X</button>
        <Galery />
      </div>
    </div>
  </section>
</template>

<script>
import Galery from "./Galery.vue"; // Asegúrate de importar el componente Galery

export default {
  components: {
    Galery,
  },
  data() {
    return {
      showGallery: false,
    };
  },
  methods: {
    openGallery() {
      this.showGallery = true;
    },
    closeGallery() {
      this.showGallery = false;
    },
  },
};
</script>

<style scoped>
.special-dish-content {
  padding-block: 70px;
}

.special-dish-banner .video-banner {
  width: 100%;
  height: 100%;
  clip-path: ellipse(80% 96% at center top);
  object-fit: cover;
  border-radius: 8px;
}

.special-dish .section-text {
  margin-block: 16px 40px;
}

.special-dish-content .wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  margin-block-end: 40px;
}

.special-dish .btn {
  margin-inline: auto;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); 
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999; 
  pointer-events: auto; 
}

.modal-content {
  background-color: #161718;
  border-radius: 8px;
  overflow-y: auto;
  width: 80%;
  z-index: 10000; 
}

.close-btn {
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  position: absolute;
  top: 20px; /* Ajusta la distancia desde la parte superior */
  right: 20px; /* Ajusta la distancia desde la parte derecha */
}

@media (max-width: 576px) {
  .special-dish-banner .video-banner {
    clip-path: none;
    margin: 0;
    width: 100%;
    height: 100%;
    border-radius: 0;
  }

  .special-dish-content {
    margin-top: -1rem;
  }

  .modal-content {
    width: 100%;
  }

}

@media (min-width: 992px) {
  .special-dish {
    display: grid;
    grid-template-columns: 1fr 1fr;
    text-align: left;
  }

  .special-dish-content {
    padding-inline: 50px 25px;
  }

  .special-dish-content .container {
    position: relative;
  }

  .special-dish-content .wrapper {
    justify-content: flex-start;
  }
}

@media (min-width: 1200px) {
  .special-dish-content {
    padding: 225px 120px;
    padding-inline-end: 0;
  }

  .special-dish-content .container {
    max-width: 460px;
    margin-inline: 0;
  }
}
</style>
