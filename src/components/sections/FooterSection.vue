<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer id="contact" class="site-footer">
    <div class="footer-main">
      <div class="footer-brand-block">
        <a class="footer-brand" href="#app">ZAQUE DEV</a>
        <p class="footer-tagline">
          Linux System Administrator focused on cloud security, with front-end
          development as a complementary skill.
        </p>
        <a class="footer-email" href="mailto:alencarisaque@proton.me">
          <span class="footer-email-icon" aria-hidden="true">
            <i class="fa-solid fa-envelope"></i>
          </span>
          <span class="footer-email-address">alencarisaque@proton.me</span>
          <i class="fa-solid fa-arrow-right footer-email-arrow" aria-hidden="true"></i>
        </a>
      </div>

      <nav class="footer-column" aria-label="Footer navigation">
        <h2 class="footer-heading">Explore</h2>
        <a class="footer-link" href="#about-me">About</a>
        <a class="footer-link" href="#about">Tech Stack</a>
        <a class="footer-link" href="#works">Projects</a>
        <a class="footer-link" href="#certific">Certificates</a>
      </nav>

      <nav class="footer-column" aria-label="Social profiles">
        <h2 class="footer-heading">Connect</h2>
        <a
          class="footer-link"
          href="https://github.com/zaquea"
          target="_blank"
          rel="noopener noreferrer"
        >GitHub</a>
        <a
          class="footer-link"
          href="https://www.linkedin.com/in/zaque-a-52262341b/"
          target="_blank"
          rel="noopener noreferrer"
        >LinkedIn</a>
        <a
          class="footer-link"
          href="https://instagram.com/zaquedev"
          target="_blank"
          rel="noopener noreferrer"
        >Instagram</a>
        <a
          class="footer-link"
          href="https://x.com/zaquedev"
          target="_blank"
          rel="noopener noreferrer"
        >X</a>
      </nav>
    </div>

    <div class="footer-bottom">
      <p class="footer-copyright">© {{ currentYear }} Zaque Dev</p>
      <div class="footer-disclosures">
        <p class="footer-attribution">
          Favicon image from
          <a
            class="footer-link"
            href="https://pngtree.com/freepng/adorable-cat-3d-model_18772753.html"
            target="_blank"
            rel="noopener noreferrer"
          >PNGTree</a>
        </p>
        <p class="footer-attribution">
          <a
            class="footer-link"
            href="https://www.flaticon.com/free-icons/cloud-security"
            target="_blank"
            rel="noopener noreferrer"
            title="Cloud security icons"
          >Cloud security icons created by RIkas Dzihab - Flaticon</a>
        </p>
        <p class="footer-privacy-note">
          Certificate details are concealed to protect personal identity.
        </p>
      </div>
      <a class="footer-link footer-back-to-top" href="#app">Back to top ↑</a>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  width: 100%;
  box-sizing: border-box;
  padding: clamp(32px, 5vw, 56px) 8% 24px;
  border-top: 1px solid rgba(98, 105, 237, 0.35);
  background: var(--bg);
  color: var(--accent);
}

.footer-main,
.footer-bottom {
  width: min(100%, 1200px);
  margin: 0 auto;
}

.footer-main {
  display: grid;
  grid-template-columns: minmax(0, 1fr) auto auto;
  gap: clamp(28px, 5vw, 72px);
  align-items: start;
}

.footer-brand {
  position: relative;
  display: inline-block;
  color: var(--accent);
  font-family: var(--heading);
  font-size: clamp(26px, 3vw, 36px);
  line-height: 1;
  text-decoration: none;
}

.footer-tagline {
  max-width: 38ch;
  margin-top: 14px;
  font-size: 15px;
  line-height: 1.6;
}

.footer-email {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  max-width: 100%;
  box-sizing: border-box;
  margin-top: 18px;
  padding: 6px 16px 6px 7px;
  border: 1px solid rgba(98, 105, 237, 0.55);
  border-radius: 999px;
  color: var(--accent);
  text-decoration: none;
  transition: color 180ms ease, background-color 180ms ease, border-color 180ms ease;
}

.footer-email:hover {
  border-color: var(--accent);
  background: var(--accent);
  color: var(--bg);
}

.footer-email:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}

.footer-email-icon {
  display: grid;
  width: 36px;
  height: 36px;
  flex: 0 0 36px;
  place-items: center;
  border-radius: 50%;
  background: var(--accent);
  color: var(--bg);
  transition: color 180ms ease, background-color 180ms ease;
}

.footer-email:hover .footer-email-icon {
  background: var(--bg);
  color: var(--accent);
}

.footer-email-address {
  min-width: 0;
  overflow-wrap: anywhere;
  font-size: 14px;
}

.footer-email-arrow {
  flex: 0 0 auto;
  font-size: 13px;
  transition: transform 180ms ease;
}

.footer-email:hover .footer-email-arrow {
  transform: translateX(3px);
}

.footer-column {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 10px;
}

.footer-heading {
  position: relative;
  margin: 0 0 8px;
  padding-bottom: 8px;
  color: var(--accent);
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.12em;
  line-height: 1.3;
  text-transform: uppercase;
}

.footer-heading::after {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 28px;
  height: 2px;
  border-radius: 999px;
  background: var(--accent);
  content: "";
}

.footer-link {
  position: relative;
  display: inline-block;
  width: fit-content;
  max-width: 100%;
  color: var(--accent);
  font-size: 14px;
  line-height: 1.4;
  text-decoration: none;
}

.footer-link::after,
.footer-brand::after {
  position: absolute;
  right: 0;
  bottom: -3px;
  left: 0;
  height: 1px;
  background: currentColor;
  content: "";
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 220ms ease;
}

.footer-link:hover::after,
.footer-link:focus-visible::after,
.footer-brand:hover::after,
.footer-brand:focus-visible::after {
  transform: scaleX(1);
}

.footer-link:focus-visible,
.footer-brand:focus-visible {
  outline: 2px solid currentColor;
  outline-offset: 4px;
  border-radius: 2px;
}

.footer-bottom {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 12px 24px;
  margin-top: 36px;
  padding-top: 18px;
  border-top: 1px solid rgba(98, 105, 237, 0.25);
  font-size: 13px;
}

.footer-copyright,
.footer-attribution,
.footer-privacy-note {
  margin: 0;
}

.footer-copyright {
  font-family: var(--mono);
}

.footer-disclosures {
  display: grid;
  gap: 6px;
  max-width: 52ch;
}

.footer-attribution,
.footer-privacy-note {
  font-size: 12px;
  line-height: 1.45;
}

.footer-privacy-note {
  opacity: 0.82;
}

@media (max-width: 760px) {
  .site-footer {
    padding: 32px 7% 20px;
  }

  .footer-main {
    grid-template-columns: minmax(0, 1fr);
    gap: 28px;
  }

  .footer-column {
    gap: 9px;
  }

  .footer-bottom {
    margin-top: 28px;
    align-items: flex-start;
    flex-direction: column;
  }
}

@media (prefers-reduced-motion: reduce) {
  .footer-link::after,
  .footer-brand::after,
  .footer-email,
  .footer-email-icon,
  .footer-email-arrow {
    transition: none;
  }
}
</style>
