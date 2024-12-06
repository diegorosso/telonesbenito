<template>
    <section class="photo-gallery">
      <div class="gallery-container">
        <div class="gallery-header">
          <h2 class="headline-1">Galería de Fotos
          </h2>
        </div>
  
        <div class="image-container">
          <img :src="images[currentIndex]" alt="photo" class="img-cover" />
        </div>
  
        <div class="controls">
          <button class="btn" @click="prevImage">
            <span class="text-1">Previous</span>
          </button>
          <button class="btn" @click="nextImage">
            <span class="text-1">Next</span>
          </button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      // Usamos import.meta.glob para cargar todas las imágenes
      const images = import.meta.glob('@/assets/imagenes/TELONES NEGROS-*.webp', { eager: true });
  
      // Extraemos las rutas de las imágenes correctamente
      return {
        currentIndex: 0,
        images: Object.keys(images).map(key => images[key].default),  // Extraemos las rutas de las imágenes
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
    height: 400px; /* Fijo el alto de la imagen para mantener el tamaño consistente */
    overflow: hidden;
  }
  
  .img-cover {
    width: 100%;
    height: 100%; /* Aseguramos que la altura también sea fija */
    object-fit: cover; /* Mantiene la imagen dentro del contenedor sin distorsionarla */
    transition: transform 0.5s ease;
  }
  
  .controls {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
  }
  
  .btn {
    background-color: transparent;
    border: 2px solid var(--gold-crayola);
    color: var(--gold-crayola);
    padding: 12px 45px;
    text-transform: uppercase;
    letter-spacing: var(--letterSpacing-5);
    font-weight: var(--weight-bold);
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }
  
  .btn .text-1 {
    color: var(--gold-crayola);
    transition: transform 0.3s ease;
  }
  
  .btn:hover .text-1 {
    transform: translateY(-5px);
  }
  
  .btn::before {
    content: "";
    position: absolute;
    bottom: 100%;
    left: 50%;
    transform: translateX(-50%);
    width: 200%;
    height: 200%;
    background-color: var(--gold-crayola);
    transition: var(--transition-2);
    z-index: -1;
  }
  
  .btn:hover::before {
    bottom: -50%;
  }
  
  @media (min-width: 992px) {
    .photo-gallery {
      padding-block: 50px;
    }
  }
  </style>
  