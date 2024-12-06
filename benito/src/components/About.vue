<template>
  <section
    class="section about text-center"
    aria-labelledby="about-label"
    id="about"
  >
    <div class="container">
      <div class="about-content">
        <p class="label-2 section-subtitle" id="about-label">Quiénes Somos</p>

        <h2 class="headline-1 section-title">Calidad en Telones para Todos</h2>

        <p class="section-text">
          Somos una empresa especializada en la fabricación de telones de alta
          calidad. Nos comprometemos a ofrecer productos duraderos y adaptados a
          las necesidades de nuestros clientes, garantizando funcionalidad y
          estilo en cada pieza.
        </p>

        <a href="#" class="btn btn-primary">
          <span class="text text-1">Conoce Más</span>

          <span class="text text-2" aria-hidden="true">Conoce Más</span>
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about .section-text {
  margin-block: 15px 30px;
}

.about .btn {
  margin-inline: auto;
  margin-block-start: 26px;
}

.about .container {
  display: grid;
  gap: 120px;
}

.about-banner {
  position: relative;
  margin-block-end: 120px;
}

.about-banner > .w-100 {
  padding-inline-start: 50px;
}

.about .abs-img {
  position: absolute;
}

.about .abs-img::before {
  z-index: -1;
}

.about .abs-img-1 {
  bottom: -120px;
  left: 0;
  width: 150px;
  padding-block: 50px;
}

.about .abs-img-2 {
  top: -65px;
  right: 0;
  overflow: hidden;
}

@media (min-width: 992px) {
  .about .container {
    gap: 30px;
  }
}

@media (min-width: 1200px) {
  .about {
    padding-block: 170px 170px;
  }
}

@media (min-width: 1400px) {
  .about-content {
    padding-inline-end: 90px;
  }

  .about .shape {
    display: block;
    top: 46%;
    left: 0;
  }
}
</style>
