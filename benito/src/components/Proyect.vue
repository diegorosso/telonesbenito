<template>
    <section class="special-dish text-center" aria-labelledby="dish-label">
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
  
          <a href="#" class="btn btn-primary">
            <span class="text text-1">Abrir Galería</span>
            <span class="text text-2" aria-hidden="true">Abrir Galería</span>
          </a>
        </div>
      </div>
  
    </section>
  </template>
  
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

  @media (max-width: 576px) {
    .special-dish-banner .video-banner{
        clip-path: none;
        margin: 0;
        width: 100%;
        height: 100%;
        border-radius: 0;
        }

        .special-dish-content{
            margin-top: -1rem;
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
  