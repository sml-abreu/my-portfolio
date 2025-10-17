<template>
  <button
    v-if="isVisible"
    @click="scrollToTop"
    class="back-to-top"
    :class="{ 'show': isVisible }"
    aria-label="Voltar ao topo"
  >
    <i class="fas fa-chevron-up"></i>
  </button>
</template>

<script>
export default {
  name: 'BackToTop',
  data() {
    return {
      isVisible: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isVisible = window.scrollY > 300
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  }
}
</script>

<style scoped>
.back-to-top {
  position: fixed;
  bottom: var(--espaco-2xg);
  right: var(--espaco-2xg);
  width: 60px;
  height: 60px;
  background: linear-gradient(45deg, var(--secundaria), var(--secundaria-hover));
  color: var(--branco);
  border: none;
  border-radius: var(--radius-total);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: var(--fonte-g);
  opacity: 0;
  transform: translateY(20px) scale(0.8);
  transition: all var(--transicao-media);
  z-index: var(--z-alto);
  box-shadow: var(--sombra-media);
}

.back-to-top:hover {
  transform: translateY(-2px) scale(1.05);
  box-shadow: var(--sombra-grande);
}

.back-to-top.show {
  opacity: 1;
  transform: translateY(0) scale(1);
}

.back-to-top i {
  transition: transform var(--transicao-media);
}

.back-to-top:hover i {
  transform: translateY(-2px);
}

/* Responsive */
@media (max-width: 768px) {
  .back-to-top {
    width: 50px;
    height: 50px;
    font-size: var(--fonte-m);
    bottom: var(--espaco-xg);
    right: var(--espaco-xg);
  }
}
</style>
