<template>
  <section id="about">
    <div class="about-heading-row">
      <h1 class="about-h">tech stack</h1>
      <div class="more">
        <a id="learn-more" href="#works">Learn More</a>
        <a
          class="learn-more-arrow"
          href="#works"
          aria-label="Ver projetos"
        >
          <i
            class="fa-solid fa-circle-arrow-right"
            id="learn-right"
            aria-hidden="true"
          ></i>
        </a>
      </div>
    </div>
    <p class="about-p">
      To me, technology is all about finding the best way <br />
      to solve real problems and create great user experiences. <br />
      Over the years, I’ve built a toolkit of tools and frameworks <br />
      I trust to bring ideas to life smoothly and efficiently. <br />
      Here’s what I work with most often:
    </p>
    <div class="tech-gallery">
      <button
        class="about-btn-1"
        aria-label="Imagem anterior"
        @click="prevImage"
      >
        <i
          class="fa-solid fa-circle-arrow-left"
          id="tech-left"
          aria-hidden="true"
        ></i>
      </button>

      <div class="tech-image-stage">
        <Transition name="fade">
          <img
            class="about-images"
            id="about-img"
            :src="images[selectedIndex]"
            :key="selectedIndex"
            alt="Ilustração da stack tecnológica"
          />
        </Transition>
      </div>

      <button
        class="about-btn-2"
        aria-label="Próxima imagem"
        @click="nextImage"
      >
        <i
          class="fa-solid fa-circle-arrow-right"
          id="tech-right"
          aria-hidden="true"
        ></i>
      </button>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import img1 from "../../assets/1-removebg-preview.png";
import img2 from "../../assets/2-removebg-preview.png";
import img3 from "../../assets/3-removebg-preview.png";
import img4 from "../../assets/4-removebg-preview.png";
import img5 from "../../assets/5-removebg-preview.png";
import img6 from "../../assets/6-removebg-preview.png";
import img7 from "../../assets/7-removebg-preview.png";
import img8 from "../../assets/8-removebg-preview.png";
import img9 from "../../assets/9-removebg-preview.png";
import img10 from "../../assets/10-removebg-preview.png";

const images = [img1, img2, img3, img4, img5, img6, img7, img8, img9, img10];
const selectedIndex = ref(0);

function nextImage() {
  selectedIndex.value++;

  if (selectedIndex.value >= images.length) {
    selectedIndex.value = 0;
  }
}

function prevImage() {
  selectedIndex.value--;

  if (selectedIndex.value < 0) {
    selectedIndex.value = images.length - 1;
  }
}
</script>

<style scoped>
#about {
  width: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  background-color: var(--bg);
  display: flex;
  flex-direction: column;
  gap: 32px;
  margin-top: 50px;
  padding: 42px 8% 56px;
}

.about-heading-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}

.about-h {
  margin: 0;
  color: var(--accent);
  font-size: clamp(58px, 10vw, 132px);
}

.more {
  display: flex;
  align-items: center;
  flex-shrink: 0;
  gap: 12px;
}

#learn-more {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 5px 40px;
  border: 1px solid transparent;
  font-size: 18px;
  background-color: var(--accent);
  color: var(--bg);
  border-radius: 50px;
  cursor: pointer;
  font-family: var(--sans);
  text-decoration: none;
  transition:
    background-color 180ms ease,
    border-color 180ms ease,
    color 180ms ease,
    transform 180ms ease;
}

#learn-more:hover,
#learn-more:focus-visible {
  transform: translateY(-2px);
  border-color: var(--accent);
  background-color: transparent;
  color: var(--accent);
}

#learn-more:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}

#learn-right {
  display: inline-block;
  flex: 0 0 auto;
  font-size: 40px;
  color: var(--accent);
  cursor: pointer;
  transform: rotate(-45deg);
  transition: translate 180ms ease, scale 180ms ease;
}

.learn-more-arrow {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: var(--accent);
  text-decoration: none;
}

.learn-more-arrow:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
  border-radius: 50%;
}

#learn-right:hover,
.learn-more-arrow:focus-visible #learn-right {
  translate: 3px -3px;
  scale: 1.06;
}

.about-p {
  color: var(--accent);
  width: min(100%, 700px);
  margin: 0 0 0 auto;
  text-align: right;
  font-size: 20px;
}

.tech-gallery {
  display: grid;
  grid-template-columns: minmax(56px, 1fr) minmax(0, 400px) minmax(56px, 1fr);
  align-items: center;
  gap: 20px;
  width: min(100%, 900px);
  margin: 0 auto;
}

.about-images {
  display: block;
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.tech-image-stage {
  position: relative;
  grid-column: 2;
  width: 100%;
  aspect-ratio: 1;
}

.about-btn-1,
.about-btn-2 {
  display: grid;
  place-items: center;
  background-color: transparent;
  cursor: pointer;
  font-family: var(--sans);
  outline: none;
  border: none;
  color: var(--accent);
}

#tech-left,
#tech-right {
  font-size: 50px;
}

.about-btn-1 {
  grid-column: 1;
}

.about-btn-2 {
  grid-column: 3;
}

.fade-enter-from {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 0.35s ease;
}

.fade-enter-to {
  opacity: 1;
}

.fade-leave-from {
  opacity: 1;
}

.fade-leave-active {
  transition: opacity 0.35s ease;
}

.fade-leave-to {
  opacity: 0;
}

@media (max-width: 640px) {
  #about {
        gap: 24px;
        padding: 32px 7% 44px;
  }
  .about-heading-row {
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
  }
  .about-p br {
        display: none;
  }
  .about-p {
        font-size: 17px;
  }
  .tech-gallery {
        grid-template-columns: 40px minmax(0, 1fr) 40px;
        gap: 12px;
  }
  .tech-image-stage {
        max-width: 320px;
  }
}

@media (max-width: 760px) {
  .about-p br {
        display: none;
  }
  #about {
        padding-right: 7%;
        padding-left: 7%;
  }
  .about-heading-row {
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
  }
  .about-p {
        font-size: 18px;
  }
}

@media (max-width: 390px) {
  .tech-gallery {
        grid-template-columns: 36px minmax(0, 1fr) 36px;
        gap: 8px;
  }
  #tech-left,
  #tech-right {
        font-size: 38px;
  }
}

@media (max-width: 760px) {
  #about {
        min-height: auto;
        padding-bottom: 24px;
  }
  .about-heading-row {
        gap: 18px;
  }
  .about-p {
        margin-top: 8px;
  }
  .tech-gallery {
        column-gap: 20px;
  }
  .about-btn-1 {
        transform: translateX(-14px);
  }
}

@media (min-width: 761px) and (max-width: 1440px) and (any-pointer: coarse) {
  #about {
        min-height: auto;
        padding-bottom: 32px;
  }
}

@media (prefers-reduced-motion: reduce) {
  #learn-more,
  #learn-right {
    transition: none;
  }
}
</style>
