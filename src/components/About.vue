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

        <p class="section-text body-3">
          Somos una empresa especializada en la fabricación de telones de alta
          calidad. Nos comprometemos a ofrecer productos duraderos y adaptados a
          las necesidades de nuestros clientes, garantizando funcionalidad y
          estilo en cada pieza.
        </p>

        <button class="btn btn-primary" @click="toggleModal">
          <span class="text text-1">Conoce Más</span>
          <span class="text text-2" aria-hidden="true">Conoce Más</span>
        </button>
      </div>
    </div>

    <!-- Modal -->
    <div v-if="isModalOpen" class="modal-overlay" @click.self="toggleModal">
      <div class="modal">
        <button class="modal-close" @click="toggleModal">×</button>
        <h3 class="title-3">Sobre Telones Benito</h3>
        <p class="body-3">
          Telones Benito es una empresa con años de experiencia en la
          fabricación de telones de alta calidad. Nuestros productos están
          diseñados para satisfacer las necesidades específicas de nuestros
          clientes, garantizando durabilidad, funcionalidad y diseño innovador.
        </p>
        <p class="body-3">
          Nos enorgullecemos de utilizar materiales de primera calidad y ofrecer
          un servicio excepcional que asegura la satisfacción de nuestros
          clientes.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isModalOpen: false,
    };
  },
  methods: {
    toggleModal() {
      this.isModalOpen = !this.isModalOpen;
    },
  },
};
</script>

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
  gap: var(--section-space);
}

/* Modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: var(--black-alpha-80);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
  padding: 20px;
}

.modal {
  background-color: var(--eerie-black-1); /* Fondo gris */
  padding: 20px;
  border-radius: var(--radius-24);
  width: 100%;
  max-width: 500px;
  box-shadow: var(--shadow-1);
  position: relative;
}

.modal-close {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: var(--fontSize-body-2);
  font-family: var(--fontFamily-dm_sans);
  cursor: pointer;
  background: none;
  border: none;
  color: #fff; /* Color claro para el botón de cerrar */
}

.modal h3 {
  margin-bottom: 15px;
  color: #fff; /* Color blanco para el título */
}

.modal p {
  margin-bottom: 10px;
  color: #fff; /* Color blanco para el texto */
}

/* Mobile styles */
@media (max-width: 768px) {
  .modal {
    padding: 15px;
    border-radius: var(--radius-24);
  }

  .modal h3 {
    font-size: var(--fontSize-title-2);
  }

  .modal p {
    font-size: var(--fontSize-body-4);
  }
}
</style>
