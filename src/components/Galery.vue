<template>
  <section class="photo-gallery">
    <div class="gallery-container">
      <div class="gallery-header">
        <h2 class="headline-1">Galería de Fotos</h2>
      </div>

      <div class="image-container">
        <img :src="images[currentIndex]" alt="photo" class="img-cover" />

        <!-- Flecha Izquierda -->
        <button class="arrow left-arrow" @click="prevImage">
          <ion-icon name="chevron-back-outline"></ion-icon>
        </button>

        <!-- Flecha Derecha -->
        <button class="arrow right-arrow" @click="nextImage">
          <ion-icon name="chevron-forward-outline"></ion-icon>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    const images = import.meta.glob("@/assets/imagenes/TELONES NEGROS-*.webp", {
      eager: true,
    });

    return {
      currentIndex: 0,
      images: Object.keys(images).map((key) => images[key].default), // Extraemos las rutas de las imágenes
    };
  },
  methods: {
    prevImage() {
      // Lógica para ir a la imagen anterior
      if (this.currentIndex > 0) {
        this.currentIndex--;
      } else {
        this.currentIndex = this.images.length - 1;
      }
    },
    nextImage() {
      // Lógica para ir a la imagen siguiente
      if (this.currentIndex < this.images.length - 1) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
    },
  },
};
</script>

<style scoped>
.photo-gallery {
  padding-block: var(--section-space);
  text-align: center;
  background-color: var(--eerie-black-1);
}

.gallery-container {
  max-width: 90%;
  margin: 0 auto;
}

.gallery-header h2 {
  color: var(--gold-crayola);
  font-size: var(--fontSize-title-1);
  font-family: var(--fontFamily-forum);
}

.image-container {
  position: relative;
  margin: 20px 0;
  width: 100%;
  height: 660px; /* Fijo el alto de la imagen */
  overflow: hidden;
}

.img-cover {
  width: 100%;
  height: 100%; /* Fijo el alto de la imagen */
  object-fit: cover;
  transition: transform 0.5s ease;
}

/* Estilo para las flechas */
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  border: none;
  color: var(--gold-crayola);
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 10;
  transition: background-color 0.3s ease;
}

.arrow:hover {
  background-color: var(--gold-crayola);
  color: var(--eerie-black-1);
}

.left-arrow {
  left: 10px; /* Ajusta la distancia del borde izquierdo */
}

.right-arrow {
  right: 10px; /* Ajusta la distancia del borde derecho */
}

.arrow ion-icon {
  font-size: 24px;
}

@media (max-width: 576px) {
  .arrow {
    width: 40px;
    height: 40px;
  }

  .arrow ion-icon {
    font-size: 20px;
  }

  .image-container {
    height: 500px;
  }
}

@media (min-width: 992px) {
  .photo-gallery {
    padding-block: 50px;
  }
}
</style>
