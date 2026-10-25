<template>
  <div class="accent" @mousemove="handleMouseMove">
    <div class="content">
      <h1 class="hero-title">ZAQUE DEV</h1>
      <img
        class="cat-top"
        :style="{
          transform: `translateX(-50%) translate(${mouseX}px, ${mouseY}px)`,
        }"
        src="../../assets/cat.png"
        alt="Hero Image"
      />
      <div class="text-container">
        <p class="left-text">
          Hi, I'm Zaque. <br />
          Linux System Administrator
        </p>
        <p class="right-text">
          Focused on cloud security, <br />
          with front-end development as <br />
          a complementary skill.
        </p>
      </div>
      <a
        href="#about"
        id="hero-down"
        aria-label="Ir para a seção Tech Stack"
      >
        <i class="fa-solid fa-circle-arrow-down" aria-hidden="true"></i>
      </a>

      <nav class="social-links" aria-label="Redes sociais">
        <a
          class="social-link"
          href="https://github.com/zaquea"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="GitHub"
        >
          <i class="fa-brands fa-square-github" aria-hidden="true"></i>
        </a>
        <a
          class="social-link"
          href="https://www.linkedin.com/in/zaque-a-52262341b/"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="LinkedIn"
        >
          <i class="fa-brands fa-square-linkedin" aria-hidden="true"></i>
        </a>
        <a
          class="social-link"
          href="https://instagram.com/zaquedev"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Instagram"
        >
          <i class="fa-brands fa-square-instagram" aria-hidden="true"></i>
        </a>
        <a
          class="social-link"
          href="https://x.com/zaquedev"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="X (Twitter)"
        >
          <i class="fa-brands fa-square-x-twitter" aria-hidden="true"></i>
        </a>
      </nav>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

console.log("Hello, world!");

const mouseX = ref(0);
const mouseY = ref(0);

const handleMouseMove = (event) => {
  const centerX = window.innerWidth / 2;
  const centerY = window.innerHeight / 2;

  mouseX.value = ((event.clientX - centerX) / centerX) * 30;
  mouseY.value = ((event.clientY - centerY) / centerY) * 15;
};
</script>

<style scoped>
.accent {
  position: relative;
  display: flex;
  background-color: var(--accent);
  width: 100%;
  height: 550px;
  border-radius: 50px;
  overflow: visible;
}

.content {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 100%;
}

.cat-top {
  position: absolute;
  top: 25px;
  left: 50%;
  transform: translateX(-50%);
  width: 600px;
  height: 600px;
  object-fit: cover;
  transition: transform 0.1s linear;
  z-index: 1;
}

.hero-title {
  position: relative;
  z-index: 0;
  width: 100%;
  color: var(--text-h);
  font-size: 180px;
  text-align: center;
  margin-top: 7px;
}

.text-container {
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding: 0 40px;
  box-sizing: border-box;
  margin-top: 20px;
}

.left-text {
  margin-top: 20px;
  text-align: left;
}

.right-text {
  margin-top: 140px;
  text-align: right;
}

#hero-down {
  position: absolute;
  bottom: 24px;
  left: 95%;
  transform: translateX(-50%);
  z-index: 2;
  display: grid;
  width: 44px;
  height: 44px;
  place-items: center;
  font-size: 40px;
  color: var(--text-h);
  text-decoration: none;
}

#hero-down:focus-visible {
  outline: 2px solid currentColor;
  outline-offset: 3px;
}

.social-links {
  position: absolute;
  bottom: 170px;
  left: 30px;
  z-index: 2;
  display: flex;
  align-items: center;
  gap: 2px;
}

.social-link {
  display: grid;
  width: 44px;
  height: 44px;
  flex: 0 0 44px;
  place-items: center;
  font-size: 40px;
  color: var(--text-h);
  line-height: 1;
  text-decoration: none;
  transition: transform 0.3s ease;
  cursor: pointer;
}

.social-link:hover,
.social-link:focus-visible {
  transform: translateY(-5px);
}

.social-link:focus-visible {
  outline: 2px solid currentColor;
  outline-offset: 3px;
}

nav {
  width: 100%;
}

a {
  text-decoration: none;
  color: var(--accent);
}

@media (max-width: 900px) {
  .accent {
        height: auto;
        border-radius: clamp(24px, 5vw, 40px);
  }
  .content {
        min-height: clamp(520px, 66vw, 600px);
  }
  .hero-title {
        margin: 50px 0 0;
        font-size: clamp(76px, 15vw, 140px);
  }
  .cat-top {
        top: clamp(48px, 8vw, 82px);
        width: min(65vw, 500px);
        height: auto;
  }
  .text-container {
        margin-top: auto;
        padding: 0 clamp(28px, 5vw, 56px) 82px;
        gap: 24px;
  }
  .left-text,
  .right-text {
        max-width: 42%;
        margin-top: 0;
        font-size: clamp(16px, 2vw, 18px);
  }
  #hero-down {
        right: clamp(28px, 5vw, 56px);
        bottom: 26px;
        left: auto;
        transform: none;
        font-size: 36px;
  }
  .social-links {
        bottom: 28px;
        left: clamp(28px, 5vw, 56px);
  }
  .social-link {
        width: 40px;
        height: 40px;
        flex-basis: 40px;
        font-size: 32px;
  }
}

@media (max-width: 760px) {
  .content {
        min-height: clamp(640px, 95vw, 740px);
  }
  .hero-title {
        font-size: clamp(68px, 15vw, 112px);
  }
  .cat-top {
        top: clamp(52px, 8vw, 66px);
        width: min(72vw, 460px);
  }
  .text-container {
        flex-direction: column;
        align-items: flex-start;
        gap: 12px;
        padding: 0 7% 88px;
  }
  .left-text,
  .right-text {
        width: 100%;
        max-width: 36rem;
        text-align: left;
  }
}

@media (max-width: 640px) {
  .content {
        min-height: clamp(620px, 125vw, 760px);
  }
  .hero-title {
        font-size: clamp(90px, 16.8vw, 100px);
  }
  .cat-top {
        top: clamp(58px, 16vw, 76px);
        width: min(80vw, 400px);
  }
  .text-container {
        padding: 0 7% 86px;
  }
  .left-text,
  .right-text {
        font-size: 16px;
  }
  .social-links {
        bottom: 24px;
        left: 7%;
        gap: 6px;
  }
  .social-link {
        width: 38px;
        height: 38px;
        flex-basis: 38px;
        font-size: 34px;
  }
  #hero-down {
        right: 7%;
        bottom: 22px;
        font-size: 32px;
  }
}

@media (max-width: 390px) {
  .hero-title {
        font-size: clamp(82px, 18vw, 96px);
  }
  .cat-top {
        width: min(90vw, 500px);
  }
}

@media (max-height: 500px) and (orientation: landscape) and (max-width: 900px) {
  .content {
        min-height: max(420px, 100svh);
  }
  .hero-title {
        font-size: clamp(54px, 11vw, 100px);
  }
  .cat-top {
        top: 46px;
        width: min(48vw, 340px);
  }
}
</style>
