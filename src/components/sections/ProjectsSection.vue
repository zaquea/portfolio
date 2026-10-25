<template>
  <section id="works">
    <h1 class="works-h">projects</h1>
    <p class="works-hero-p">
      Some of the things I've built while learning, experimenting, and <br />
      putting my ideas into practice. Each project has taught <br />
      me something new and helped me become a better developer.
    </p>
    <div class="view-all">
      <button
        id="view-more"
        type="button"
        @click="openLink('https://github.com/zaquea?tab=repositories')"
      >
        View All
      </button>
      <a
        href="https://github.com/zaquea?tab=repositories"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Ver todos os projetos no GitHub"
      >
        <i
          class="fa-solid fa-circle-arrow-right fa-rotate-by"
          id="works-right"
          style="color: #6269ed; --fa-rotate-angle: -40deg"
          aria-hidden="true"
        ></i>
      </a>
    </div>
    <div class="projects-summary">
      <div class="project-item">
        <span class="project-year">2026</span>

        <div class="project-info">
          <h3>My first project: Bible</h3>
          <p>
            A Bible-centered web project that gave me hands-on front-end
            experience and helped turn an idea into a usable digital product.
          </p>
        </div>

        <button
          class="project-btn"
          type="button"
          @click="openLink('https://github.com/zaquea/Bible')"
        >
          Discover
        </button>
      </div>

      <div class="project-item featured">
        <span class="project-year">2026</span>

        <div class="project-info">
          <h3>This portfolio</h3>
          <p>
            My portfolio brings together selected work and the skills I’m
            developing in Linux system administration, cloud security, and
            front-end development.
          </p>
        </div>

        <button
          class="project-btn"
          type="button"
          @click="openLink('https://github.com/zaquea/portfolio')"
        >
          Discover
        </button>
      </div>

      <div class="project-item">
        <span class="project-year">2026</span>

        <div class="project-info">
          <h3>Server status project</h3>
          <p>
            A hands-on Linux and Bash project focused on checking server status
            and applying practical system-administration concepts.
          </p>
        </div>

        <button
          class="project-btn"
          type="button"
          @click="openLink('https://github.com/zaquea/server_status')"
        >
          Discover
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
function openLink(url) {
  window.open(url, "_blank", "noopener,noreferrer");
}
</script>

<style scoped>
#works {
  width: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  background-color: var(--bg);
  margin-top: 50px;
  padding: 64px 8% 72px;
}

.works-h {
  margin: 0 0 12px;
  color: var(--accent);
  font-size: clamp(64px, 12vw, 140px);
  text-align: right;
}

.works-hero-p {
  width: min(100%, 700px);
  margin: 0 0 30px auto;
  margin-top: 40px;
  text-align: right;
  font-size: 20px;
  color: var(--accent);
}

.view-all {
  display: flex;
  align-items: center;
  gap: 12px;
  margin: 0 0 28px;
}

#view-more {
  padding: 5px 40px;
  border: 1px solid transparent;
  font-size: 18px;
  background-color: var(--accent);
  color: var(--bg);
  border-radius: 50px;
  cursor: pointer;
  font-family: var(--sans);
  outline: none;
  transition:
    background-color 180ms ease,
    border-color 180ms ease,
    color 180ms ease,
    transform 180ms ease;
}

#view-more:hover,
#view-more:focus-visible {
  transform: translateY(-2px);
  border-color: var(--accent);
  background-color: transparent;
  color: var(--accent);
}

#view-more:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}

#works-right {
  font-size: 40px;
  cursor: pointer;
  transition: translate 180ms ease, scale 180ms ease;
}

#works-right:hover,
.view-all > a:focus-visible #works-right {
  translate: 3px -3px;
  scale: 1.06;
}

.view-all > a:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
  border-radius: 50%;
}

.projects-summary {
  display: flex;
  flex-direction: column;
  max-width: 1100px;
  width: 100%;
  margin: 0 auto;
}

.project-item {
  display: grid;
  grid-template-columns: 90px 1fr 110px;
  align-items: center;
  gap: 30px;
  padding: 32px 16px;
  border-top: 1px solid rgba(220, 255, 150, 0.35);
}

.project-item:last-child {
  border-bottom: 1px solid rgba(220, 255, 150, 0.35);
}

.project-year {
  color: var(--accent);
  font-family: var(--mono);
}

.project-info {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.project-info h3 {
  color: var(--accent);
  margin: 0;
  font-size: 16px;
  text-align: left;
}

.project-info p {
  color: var(--accent);
  text-align: left;
  max-width: 520px;
  margin: 0;
  font-size: 13px;
  line-height: 1.4;
}

.project-btn {
  width: 90px;
  height: 30px;
  border: 1px solid rgba(220, 255, 150, 0.5);
  border-radius: 999px;
  background: transparent;
  color: var(--accent);
  font-size: 12px;
  cursor: pointer;
  transition: 0.25s ease;
}

.project-item.featured {
  margin: 0;
  padding: 32px 16px;
  border: none;
  border-radius: 24px;
  background: var(--accent);
  color: var(--bg);
}

.project-item.featured .project-btn {
  background: var(--bg);
  color: var(--accent);
  border: none;
  outline: none;
}

.project-item.featured h3 {
  color: var(--bg);
}

.project-item.featured p {
  color: var(--bg);
}

.project-item.featured .project-year {
  color: var(--bg);
}

@media (max-width: 640px) {
  #works {
    padding: 48px 7%;
  }
  .works-hero-p br {
    display: none;
  }
  .project-item {
    grid-template-columns: 55px minmax(0, 1fr);
    gap: 14px;
    padding: 24px 8px;
  }
  .project-btn {
    grid-column: 2;
  }
}

@media (max-width: 760px) {
  .works-hero-p br {
    display: none;
  }
  #works {
    padding-right: 7%;
    padding-left: 7%;
  }
  .works-hero-p {
    font-size: 18px;
  }
}

@media (max-width: 390px) {
  .project-item {
    grid-template-columns: 46px minmax(0, 1fr);
    gap: 10px;
    padding-right: 0;
    padding-left: 0;
  }
  .project-info h3 {
    font-size: 15px;
  }
  .project-btn {
    width: 82px;
  }
}

@media (max-width: 760px) {
  #works {
    margin-top: 24px;
  }
}

@media (min-width: 761px) and (max-width: 1440px) and (any-pointer: coarse) {
  #works {
    margin-top: 24px;
  }
}

@media (prefers-reduced-motion: reduce) {
  #view-more,
  #works-right {
    transition: none;
  }
}
</style>
