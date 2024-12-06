<template>
  <div class="topbar">
    <div class="container">
      <!-- Dirección -->
      <a
        href="https://www.google.com/maps?q=Av.+Garc%C3%ADa+del+R%C3%ADo+2416,+Aut%C3%B3noma+de+Buenos+Aires"
        target="_blank"
        class="topbar-item link"
      >
        <div class="icon">
          <ion-icon name="location-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">
          Av. García del Río 2416. Autónoma de Buenos Aires
        </span>
      </a>

      <div class="topbar-item item-2"></div>

      <!-- Teléfono -->
      <a href="tel:+11234567890" class="topbar-item link">
        <div class="icon">
          <ion-icon name="call-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">011 4940 2373</span>
      </a>

      <div class="separator"></div>

      <!-- Correo -->
      <a href="mailto:telonesbenito@gmail.com" class="topbar-item link">
        <div class="icon">
          <ion-icon name="mail-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">telonesbenito@gmail.com</span>
      </a>
    </div>
  </div>
</template>

<style>
.topbar {
  display: none;
}

@media (min-width: 575px) {
  .topbar {
    background-color: transparent;
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding-block: 10px;
    border-block-end: 1px solid var(--white-alpha-20);
    z-index: 9999; 
    transition: var(--transition-1);
  }

  .topbar:has(~ .header.active) {
    transform: translateY(-100%);
  }

  .topbar-item:not(.link),
  .topbar .separator {
    display: none;
  }

  .topbar .container,
  .topbar-item {
    display: flex;
    align-items: center;
  }

  .topbar .container {
    justify-content: center;
    gap: 30px;
  }

  .topbar-item {
    gap: 6px;
  }

  .topbar-item ion-icon {
    --ionicon-stroke-width: 60px;
  }

  .topbar-item .span {
    font-size: var(--fontSize-label-1);
  }

  .topbar .link {
    transition: var(--transition-1);
  }

  .topbar .link:is(:hover, :focus-visible) {
    color: var(--gold-crayola);
  }
}

@media (min-width: 768px) {
}

@media (min-width: 992px) {
  .topbar-item:not(.link) {
    display: flex;
  }

  .topbar .item-2 {
    margin-inline-end: auto;
  }
}

@media (min-width: 1200px) {
  .topbar .container {
    max-width: unset;
  }

  .topbar .separator {
    display: block;
  }
}

@media (min-width: 1400px) {
}
</style>
