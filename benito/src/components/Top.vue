<template>
  <div class="topbar">
    <div class="container">
      <address class="topbar-item">
        <div class="icon">
          <ion-icon name="location-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">
            Núñez, CABA
        </span>
      </address>

      <div class="topbar-item item-2">

      </div>

      <a href="tel:+11234567890" class="topbar-item link">
        <div class="icon">
          <ion-icon name="call-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">+1 123 456 7890</span>
      </a>

      <div class="separator"></div>

      <a href="mailto:booking@restaurant.com" class="topbar-item link">
        <div class="icon">
          <ion-icon name="mail-outline" aria-hidden="true"></ion-icon>
        </div>

        <span class="span">telonesbenito@gmail.com</span>
      </a>
    </div>
  </div>
</template>

<style>
.topbar{display: none;}
@media (min-width: 575px) {
  .topbar {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding-block: 10px;
    border-block-end: 1px solid var(--white-alpha-20);
    z-index: 4;
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
