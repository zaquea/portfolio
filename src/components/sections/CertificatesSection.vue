<template>
  <section id="certific">
    <div class="certific-intro">
      <h1 class="certific-h">certificates</h1>
      <p class="certific-p">
        These are some of the certificates I've earned through online courses
        and<br />
        training programs. They represent my commitment to continuous
        learning<br />
        and my dedication to improving my skills.
      </p>
    </div>

    <button
      class="certificate-featured"
      type="button"
      :aria-label="`Ampliar ${certificates[selectedCertificateIndex].alt}`"
      @click="isCertificateOpen = true"
    >
      <img
        :src="certificates[selectedCertificateIndex].image"
        :alt="certificates[selectedCertificateIndex].alt"
        :width="certificates[selectedCertificateIndex].width"
        :height="certificates[selectedCertificateIndex].height"
      />
    </button>

    <div class="certific-content">
      <div id="certific-imgs" role="group" aria-label="Todos os certificados">
        <button
          v-for="item in certificateCards"
          :key="item.index"
          class="certificate-card"
          :class="{ 'is-selected': item.index === selectedCertificateIndex }"
          type="button"
          :aria-label="`Mostrar ${item.certificate.alt} em destaque`"
          @click="selectedCertificateIndex = item.index"
        >
          <img :src="item.certificate.image" :alt="item.certificate.alt" />
        </button>
      </div>
      <p class="certificate-count" aria-live="polite">
        {{ selectedCertificateIndex + 1 }} / {{ certificates.length }}
      </p>
    </div>

    <div
      v-if="isCertificateOpen"
      class="certificate-lightbox"
      role="dialog"
      aria-modal="true"
      :aria-label="certificates[selectedCertificateIndex].alt"
      @click.self="isCertificateOpen = false"
      @keydown.esc.window="isCertificateOpen = false"
      tabindex="-1"
    >
      <button
        class="certificate-close"
        type="button"
        aria-label="Fechar certificado"
        @click="isCertificateOpen = false"
      >
        <i class="fa-solid fa-xmark" aria-hidden="true"></i>
      </button>
      <img
        :src="certificates[selectedCertificateIndex].image"
        :alt="certificates[selectedCertificateIndex].alt"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import mimoHtml from "../../assets/certs/mimohtml.png";
import mimoCss from "../../assets/certs/mimocss.png";
import obli25 from "../../assets/certs/eng25.png";
import obli26 from "../../assets/certs/eng26.png";
import obne26 from "../../assets/certs/ent26.png";

const certificates = [
  { image: mimoHtml, alt: "Certificado de HTML — Mimo", width: 596, height: 843 },
  { image: mimoCss, alt: "Certificado de CSS — Mimo", width: 596, height: 843 },
  { image: obli25, alt: "Certificado OBLI 25", width: 842, height: 596 },
  { image: obli26, alt: "Certificado OBLI 26", width: 842, height: 596 },
  { image: obne26, alt: "Certificado OBNE 26", width: 842, height: 596 },
];
const certificateCards = certificates.map((certificate, index) => ({
  certificate,
  index,
}));

const selectedCertificateIndex = ref(Math.floor(certificates.length / 2));
const isCertificateOpen = ref(false);
</script>

<style scoped>
#certific {
  width: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 42px 0 72px;
  background-color: var(--bg);
}

.certific-intro {
  width: min(1000px, 82%);
  margin: 0 auto 28px;
}

.certificate-featured {
  display: flex;
  align-items: center;
  justify-content: center;
  width: calc(100% + 14px);
  margin-left: -7px;
  padding: 0;
  border: 0;
  background: var(--bg);
  cursor: zoom-in;
}

.certificate-featured img {
  display: block;
  width: auto;
  height: auto;
  max-width: 100%;
  object-fit: contain;
  object-position: center;
}

.certific-content {
  width: min(100%, 1000px);
  box-sizing: border-box;
  padding: 30px 0 0;
  margin: 0 auto;
}

#certific-imgs {
  display: grid;
  grid-template-columns: repeat(5, minmax(0, 1fr));
  gap: clamp(10px, 1.6vw, 18px);
  width: 100%;
}

.certificate-card {
  display: block;
  aspect-ratio: 1;
  min-width: 0;
  margin: 0;
  padding: 0;
  overflow: hidden;
  border: 0;
  border-radius: clamp(26px, 5vw, 40px);
  background: var(--accent);
  cursor: pointer;
  transition: transform 250ms ease;
  opacity: 0.78;
}

.certificate-card:hover {
  opacity: 1;
  transform: scale(1.03);
}

.certificate-card.is-selected {
  opacity: 1;
  box-shadow: inset 0 0 0 3px var(--accent);
}

.certificate-card:focus-visible {
  outline: 3px solid var(--accent);
  outline-offset: 5px;
}

.certificate-card img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.certificate-count {
  font-family: var(--mono);
  margin-top: 16px;
  color: var(--accent);
  text-align: center;
  font-size: 14px;
}

.certific-h {
  margin: 0 0 12px;
  color: var(--accent);
  font-size: clamp(64px, 12vw, 140px);
  line-height: 1;
  text-align: left;
}

.certific-p {
  color: var(--accent);
  max-width: 700px;
  margin: 0;
  font-size: 18px;
  text-align: left;
  margin-bottom: 80px;
}

.certificate-lightbox {
  position: fixed;
  z-index: 10;
  inset: 0;
  display: grid;
  place-items: center;
  padding: 56px 24px 24px;
  background: rgba(14, 3, 108, 0.94);
  cursor: zoom-out;
}

.certificate-lightbox img {
  display: block;
  max-width: min(100%, 1000px);
  max-height: 100%;
  object-fit: contain;
  cursor: default;
}

.certificate-close {
  position: absolute;
  top: 18px;
  right: 22px;
  display: grid;
  width: 44px;
  height: 44px;
  place-items: center;
  border: 1px solid var(--accent);
  border-radius: 50%;
  background: var(--bg);
  color: var(--accent);
  font-size: 22px;
  cursor: pointer;
}

@media (max-width: 640px) {
  #certific {
        padding: 32px 0 44px;
  }
  .certific-intro {
        width: 86%;
        margin-bottom: 22px;
  }
  .certific-content {
        padding: 18px 7% 0;
  }
  #certific-imgs {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 12px;
  }
  .certificate-card:last-child:nth-child(odd) {
        grid-column: 1 / -1;
        justify-self: center;
        width: calc(50% - 6px);
  }
  .certific-p br {
        display: none;
  }
  .certific-p {
        font-size: 16px;
  }
  .certificate-lightbox {
        padding: 64px 16px 16px;
  }
}

@media (max-width: 760px) {
  .certific-p br {
        display: none;
  }
  .certific-intro {
        width: 86%;
  }
  .certificate-featured {
        width: 100%;
        margin-left: 0;
        padding: 0 7%;
        box-sizing: border-box;
  }
}

@media (max-width: 640px) {
  .certificate-featured {
        padding: 0;
  }
}
</style>
