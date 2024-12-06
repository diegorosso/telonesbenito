<template>
  <section class="reservation">
    <div class="container">
      <div class="form reservation-form bg-black-10">
        <form action="" class="form-left">
          <h2 class="headline-1 text-center">Contacto</h2>

          <p class="form-text text-center">Contáctanos para más información.</p>

          <div class="input-wrapper">
            <input
              type="text"
              name="name"
              placeholder="Nombre"
              autocomplete="off"
              class="input-field"
            />

            <input
              type="text"
              name="lastName"
              placeholder="Apellido"
              autocomplete="off"
              class="input-field"
            />
          </div>

          <div class="input-wrapper">
            <input
              type="mail"
              name="mail"
              placeholder="Mail"
              autocomplete="off"
              class="input-field"
            />
            <input
              type="tel"
              name="phone"
              placeholder="Teléfono"
              autocomplete="off"
              class="input-field"
            />
          </div>

          <textarea
            name="message"
            placeholder="Message"
            autocomplete="off"
            class="input-field"
          ></textarea>

          <button type="submit" class="btn btn-secondary">
            <span class="text text-1">Enviar Mensaje</span>

            <span class="text text-2" aria-hidden="true">Enviar Mensaje</span>
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<style>
.reservation{
  padding-block: 170px 170px
}
.form-text {
  margin-block-end: 40px;
}

.form-text .link {
  display: inline;
  color: var(--gold-crayola);
}

.form-right .headline-1 {
  margin-block-end: 40px;
}

.form-right .contact-label {
  margin-block-end: 5px;
}

.form-right .separator {
  margin: 20px auto;
}

.form-right .body-4 {
  color: var(--quick-silver);
  line-height: var(--lineHeight-3);
}

.form-right .body-4:not(:last-child) {
  margin-block-end: 25px;
}

.form-left,
.form-right {
  padding: 40px 20px 30px;
}

.input-field[type="date"] {
  text-transform: uppercase;
  padding-inline-end: 10px;
}

.input-field[type="date"]::-webkit-calendar-picker-indicator {
  opacity: 0;
}

textarea.input-field {
  resize: none;
  height: 140px;
  padding-block: 20px;
  line-height: var(--lineHeight-1);
}

.form-left .btn {
  max-width: 100%;
  width: 100%;
}

.form-right {
  background-repeat: repeat;
  background-position: top left;
}

@media (min-width: 768px) {
  .reservation .input-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 20px;
  }

  .reservation .input-wrapper:nth-child(4) {
    grid-template-columns: repeat(1fr 1fr);
  }
}

@media (min-width: 992px) {
  .reservation-form {
    display: grid;
    grid-template-columns: 1fr ;
  }
}
</style>
