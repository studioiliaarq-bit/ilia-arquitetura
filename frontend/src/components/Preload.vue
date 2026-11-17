
<template>
  <div class="preload" v-if="isLoading">

    <div class="architecture">

      <span class="studio-name">STUDIO ILIA</span>

      <svg viewBox="0 0 400 300" class="house">

        <!-- Linhas de referência -->
        <path d="M40 245 H360" class="line reference"/>

        <!-- Fundação -->
        <path d="M90 225 H310" class="line foundation"/>

        <!-- Paredes externas -->
        <path d="M100 225 V115" class="line wall"/>
        <path d="M300 225 V115" class="line wall"/>

        <!-- Telhado -->
        <path d="M65 125 L200 35 L335 125" class="line roof"/>

        <!-- Estrutura superior -->
        <path d="M100 115 L200 50 L300 115" class="line structure"/>

        <!-- Divisão interna -->
        <path d="M200 115 V225" class="line detail"/>

        <!-- Porta -->
        <path d="M170 225 V155 H230 V225" class="line detail"/>

        <!-- Janela esquerda -->
        <path d="M115 140 H165 V185 H115 Z" class="line window window-left"/>
        <path d="M140 140 V185 M115 162 H165" class="line detail window-left"/>

        <!-- Janela direita -->
        <path d="M235 140 H285 V185 H235 Z" class="line window window-right"/>
        <path d="M260 140 V185 M235 162 H285" class="line detail window-right"/>

        <!-- Chaminé -->
        <path d="M265 82 V43 H290 V95" class="line detail"/>

        <!-- Detalhes do telhado -->
        <path d="M85 112 L200 35 L315 112" class="line detail"/>

      </svg>

      <div class="loading-info">
        <span>Projetando espaços, criando histórias.</span>
        <span>{{ progress }}%</span>
      </div>

      <div class="progress-track">
        <div
          class="progress"
          :style="{ width: progress + '%' }"
        ></div>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: 'Preload',

  data() {
    return {
      isLoading: true,
      progress: 0,
      interval: null
    }
  },

  mounted() {
    this.animateProgress()
  },

  beforeUnmount() {
    clearInterval(this.interval)
  },

  methods: {
    animateProgress() {
      this.interval = setInterval(() => {
        if (this.progress < 100) {
          this.progress += 1
        } else {
          clearInterval(this.interval)

          setTimeout(() => {
            this.isLoading = false
          }, 700)
        }
      }, 35)
    }
  }
}
</script>

<style scoped>
.preload {
  position: fixed;
  inset: 0;
  z-index: 99999;
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--color-1);
  color: var(--color-7);
}

.architecture {
  width: min(400px, 85%);
}

.studio-name {
  display: block;
  text-align: center;
  font-size: 1.2rem;
  letter-spacing: 7px;
  margin-bottom: 35px;
  color: var(--color-7);
}

.house {
  width: 100%;
  overflow: visible;
}

/* Animação dos traços */

.line {
  fill: none;
  stroke: var(--color-7);
  stroke-width: 1.3;
  stroke-linecap: round;
  stroke-linejoin: round;

  stroke-dasharray: 500;
  stroke-dashoffset: 500;

  animation: draw 1s ease forwards;
}

.reference {
  opacity: .4;
  animation-delay: .1s;
}

.foundation {
  animation-delay: .3s;
}

.wall {
  animation-delay: .7s;
}

.roof {
  animation-delay: 1.2s;
}

.structure {
  animation-delay: 1.7s;
}

.detail {
  animation-delay: 2.2s;
}

.window-left {
  animation-delay: 2.7s;
}

.window-right {
  animation-delay: 3.7s;
}

@keyframes draw {
  to {
    stroke-dashoffset: 0;
  }
}

/* Carregamento */

.loading-info {
  display: flex;
  justify-content: space-between;
  letter-spacing: .5px;
  margin-top: 25px;
  margin-bottom: 12px;
}

.loading-info span {
  font-size: 0.9rem;
  color: var(--color-7);
}



.progress-track {
  height: 1px;
  background: var(--color-4);
}

.progress {
  height: 100%;
  background: var(--color-7);
  transition: width .1s linear;
}

/* Saída */

.preload {
  animation: appear .5s ease;
}

@keyframes appear {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>
