<template>
  <footer
    class="footer section has-bg-image text-center backgound"
  >
    <div class="container">
      <div class="footer-top grid-list">
        <ul class="footer-list">
          <li>
            <a href="#" class="label-2 footer-link hover-underline">Facebook</a>
          </li>

          <li>
            <a href="#" class="label-2 footer-link hover-underline"
              >Instagram</a
            >
          </li>

          <li>
            <a href="#" class="label-2 footer-link hover-underline">Youtube</a>
          </li>

          <li>
            <a href="#" class="label-2 footer-link hover-underline"
              >Google Map</a
            >
          </li>
        </ul>
      </div>

      <div class="footer-bottom">
        <p class="copyright">
          &copy; 2024. | Diseñado por
          <a
            href=""
            target="_blank"
            class="link"
            >BUG</a
          >
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>

.backgound{
  background-color:var(--black-alpha-80);
}
.footer-top {
  margin-block-end: 70px;
}



.footer-brand::before {
  left: 0;
}

.footer-brand::after {
  right: 0;
}

.footer-brand .logo {
  max-width: max-content;
  margin-inline: auto;
  margin-block-end: 40px;
}

.footer-brand :is(.body-4, .label-1) {
  color: var(--quick-silver);
  line-height: var(--lineHeight-3);
}

.footer-brand .contact-link {
  margin-block: 6px;
  transition: var(--transition-1);
}

.footer-brand .contact-link:is(:hover, :focus-visible) {
  color: var(--gold-crayola);
}

.footer-brand .wrapper {
  display: flex;
  justify-content: center;
  gap: 2px;
  margin-block: 40px 25px;
}

.footer-brand .separator {
  animation: rotate360 15s linear infinite;
}

.footer-brand .label-1 {
  margin-block-end: 30px;
}

.footer-brand .label-1 .span {
  display: inline;
  color: var(--white);
}

.footer-brand .icon-wrapper .input-field {
  cursor: text;
}

.footer-brand .btn {
  min-width: 100%;
}

.footer-list {
  display: flex;
  justify-content: space-around;
  gap: 20px;
}

.footer-link {
  color: var(--quick-silver);
  font-weight: var(--weight-bold);
  text-transform: uppercase;
  letter-spacing: var(--letterSpacing-4);
  margin-inline: auto;
  transition: var(--transition-1);
}

.footer-link:is(:hover, :focus-visible) {
  color: var(--gold-crayola);
}

.copyright {
  color: var(--quick-silver);
  line-height: var(--lineHeight-3);
}

.copyright .link {
  display: inline;
  color: var(--gold-crayola);
  text-decoration: underline;
}
@media (max-width: 575px) {
    .footer-list{
        display: flex;
        flex-direction: column;
    }
}

@media (min-width: 768px) {
  .footer-brand {
    grid-column: 1 / 3;
  }
  .grid-list{
    grid-template-columns:  1fr;
  }
}
@media (min-width: 992px) {
  .footer .grid-list {
    grid-template-columns:  1fr;
    align-items: center;
  }

  .footer-brand {
    grid-column: auto;
    order: 1;
    padding-block: 100px;
  }

  .footer-list:last-child {
    order: 2;
  }
}
</style>
