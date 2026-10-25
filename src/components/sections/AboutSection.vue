<template>
  <section
    id="about-me"
    class="about-me-section"
    aria-labelledby="about-me-title"
  >
    <nav class="sections-nav" aria-label="Section navigation">
      <ul class="nav-links">
        <li><a href="#about-me">About</a></li>
        <li><a href="#about">Stack</a></li>
        <li><a href="#works">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
    <div class="about-me-layout">
      <div class="about-copy">
        <div class="about-heading-wrap">
          <h2 id="about-me-title" class="about-title">
            <span>about</span>
            <span>me</span>
          </h2>
          <svg
            class="about-heading-arrow"
            viewBox="0 0 72 86"
            fill="none"
            aria-hidden="true"
          >
            <path d="M65 5C58 35 48 54 16 75" />
            <path d="m17 58-2 18 18-2" />
          </svg>
        </div>

        <div class="about-role">
          <p>Linux System Administrator</p>
          <span aria-hidden="true"></span>
        </div>

        <p class="about-description">
          I’m focused on cloud security and reliable Linux systems. I also work
          in front-end development, bringing a systems perspective to clear,
          dependable user experiences.
        </p>

        <a
          class="about-cta"
          href="mailto:alencarisaque@proton.me"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="E-Mail"
        >
          <span>Let’s talk</span>
          <span class="about-cta-icon" aria-hidden="true">
            <i class="fa-solid fa-arrow-right"></i>
          </span>
        </a>
      </div>

      <div class="about-visual">
        <div class="about-portrait-frame">
          <img
            src="../../assets/cat-me.jpg"
            alt="An orange kitten relaxing on a sofa"
            loading="lazy"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-me-section {
  width: 100%;
  box-sizing: border-box;
  padding: clamp(64px, 8vw, 112px) 8%;
  background: var(--bg);
  color: var(--accent);
}

.sections-nav {
  width: min(100%, 1320px);
  margin: 0 auto 32px;
}

.nav-links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 18px clamp(24px, 7vw, 100px);
  margin: 0;
  padding: 0;
  list-style: none;
}

.nav-links a {
  display: inline-flex;
  align-items: center;
  padding: 8px 14px;
  border: 1px solid transparent;
  border-radius: 999px;
  color: var(--accent);
  text-decoration: none;
  transition:
    background-color 180ms ease,
    border-color 180ms ease,
    transform 180ms ease;
}

.nav-links a:hover,
.nav-links a:focus-visible {
  transform: translateY(-2px);
  border-color: rgba(98, 105, 237, 0.48);
  background-color: rgba(98, 105, 237, 0.12);
}

.nav-links a:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
}

@media (prefers-reduced-motion: reduce) {
  .nav-links a {
    transition: none;
  }
}

.about-me-layout {
  display: grid;
  grid-template-columns: minmax(0, 1.08fr) minmax(300px, 0.92fr);
  align-items: center;
  gap: clamp(40px, 6vw, 96px);
  width: min(100%, 1320px);
  margin: 0 auto;
}

.about-copy {
  position: relative;
  min-width: 0;
  text-align: left;
}

.about-heading-wrap {
  position: relative;
  margin: 28px 0 22px;
}

.about-title {
  display: flex;
  align-items: baseline;
  gap: 0.12em;
  margin: 0;
  color: var(--accent);
  font-family: var(--heading);
  font-size: clamp(68px, 8.7vw, 132px);
  line-height: 0.88;
  white-space: nowrap;
}

.about-heading-arrow {
  position: absolute;
  top: -18px;
  right: -18px;
  width: clamp(48px, 6vw, 82px);
  overflow: visible;
  stroke: var(--accent);
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 2;
}

.about-role {
  display: flex;
  align-items: center;
  gap: 20px;
  margin: 0 0 20px;
}

.about-role p {
  margin: 0;
  color: var(--accent);
  font-size: clamp(20px, 2.1vw, 30px);
  line-height: 1.25;
}

.about-role span {
  width: 54px;
  height: 2px;
  flex: 0 0 auto;
  background: var(--accent);
}

.about-description {
  max-width: 56ch;
  margin: 0;
  color: var(--accent);
  font-size: clamp(16px, 1.35vw, 19px);
  line-height: 1.65;
}

.about-cta {
  display: inline-flex;
  align-items: center;
  justify-content: space-between;
  gap: 28px;
  min-width: 230px;
  min-height: 56px;
  box-sizing: border-box;
  margin-top: 32px;
  padding: 5px 7px 5px 24px;
  border: 1px solid var(--accent);
  border-radius: 999px;
  color: var(--accent);
  font-size: 17px;
  text-decoration: none;
  transition:
    background-color 180ms ease,
    color 180ms ease;
}

.about-cta:hover {
  background: var(--accent);
  color: var(--bg);
}

.about-cta:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}

.about-cta-icon {
  display: grid;
  width: 40px;
  height: 40px;
  flex: 0 0 40px;
  place-items: center;
  border-radius: 50%;
  background: var(--accent);
  color: var(--bg);
  transition:
    background-color 180ms ease,
    color 180ms ease;
}

.about-cta:hover .about-cta-icon {
  background: var(--bg);
  color: var(--accent);
}

.about-visual {
  display: grid;
  min-width: 0;
  place-items: center;
}

.about-portrait-frame {
  position: relative;
  width: min(100%, 520px);
  aspect-ratio: 1;
  border: 2px solid var(--accent);
  border-radius: 47% 53% 58% 42% / 42% 44% 56% 58%;
}

.about-portrait-frame::after {
  position: absolute;
  z-index: 0;
  inset: -12px;
  border: 1px solid color-mix(in srgb, var(--accent) 58%, transparent);
  border-radius: 56% 44% 47% 53% / 48% 42% 58% 52%;
  content: "";
  pointer-events: none;
  transform: rotate(-4deg);
}

.about-portrait-frame img {
  display: block;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  object-fit: cover;
  object-position: center;
}

@media (max-width: 900px) {
  .about-me-section {
    padding-right: 7%;
    padding-left: 7%;
  }

  .about-me-layout {
    grid-template-columns: minmax(0, 1.05fr) minmax(250px, 0.95fr);
    gap: 32px;
  }

  .about-heading-arrow {
    right: -4px;
  }
}

@media (max-width: 760px) {
  .about-me-section {
    padding: 56px 7% 64px;
  }

  .about-me-layout {
    grid-template-columns: minmax(0, 1fr);
    gap: 44px;
  }

  .about-heading-wrap {
    margin-top: 24px;
  }

  .about-title {
    font-size: clamp(64px, 13vw, 94px);
  }

  .about-heading-arrow {
    display: none;
  }

  .about-description {
    max-width: 60ch;
    font-size: 17px;
  }

  .about-visual {
    width: min(100%, 460px);
    justify-self: center;
  }
}

@media (max-width: 390px) {
  .about-title {
    font-size: clamp(58px, 14vw, 72px);
  }

  .about-role {
    gap: 12px;
  }

  .about-role p {
    font-size: 20px;
  }

  .about-role span {
    width: 32px;
  }

  .about-cta {
    min-width: 210px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .about-cta,
  .about-cta-icon {
    transition: none;
  }
}
</style>
