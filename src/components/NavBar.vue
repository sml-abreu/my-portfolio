<template>
  <header>
    <div class="header-content">
      <div class="logo-container">
        <img src="/logo.png" alt="Logo" class="logo" />
        <button @click="toggleMenu" class="menu-arrow" :class="{ 'open': isMenuOpen }">
          <i class="fas fa-chevron-down"></i>
        </button>
      </div>
      <div class="social-icons">
        <a href="#" class="social-icon whatsapp"><i class="fab fa-whatsapp"></i></a>
        <a href="#" class="social-icon github"><i class="fab fa-github"></i></a>
        <a href="#" class="social-icon instagram"><i class="fab fa-instagram"></i></a>
      </div>
    </div>
    
    <!-- Menu de navegação -->
    <transition name="fade-menu">
      <nav v-if="isMenuOpen" class="navigation-menu">
        <ul class="menu-items">
          <li class="menu-item" :style="{ animationDelay: '0.1s' }"><a href="#sobre" @click="scrollToSection">Sobre Mim</a></li>
          <li class="menu-item" :style="{ animationDelay: '0.2s' }"><a href="#experiencia" @click="scrollToSection">Experiência</a></li>
        </ul>
      </nav>
    </transition>
  </header>
</template>

<style scoped>
header {
  background: var(--transparente);
  padding: var(--espaco-p) var(--espaco-2xg);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: var(--z-maximo);
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: var(--z-alto);
}

.logo-container {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  gap: var(--espaco-m);
}

.logo {
  height: 50px;
  width: auto;
  object-fit: contain;
  animation: logoSlideIn 1s ease-out 0.3s both;
}

.social-icons {
  display: flex;
  font-size: var(--fonte-2xg);
  gap: var(--espaco-2xg);
  position: relative;
  z-index: var(--z-alto);
  animation: socialIconsSlideIn 1s ease-out 1.2s both;
}

.social-icon {
  background: var(--transparente);
  padding: var(--espaco-xp);
  border-radius: var(--radius-total);
  transition: transform var(--transicao-lenta) !important;
  animation: socialIconBounce 0.6s ease-out both;
}

.social-icon:nth-child(1) {
  animation-delay: 1.4s;
}
.social-icon:nth-child(2) {
  animation-delay: 1.6s;
}
.social-icon:nth-child(3) {
  animation-delay: 1.8s;
}

.social-icon:hover {
  transform: scale(1.2) !important;
}

.social-icon.whatsapp {
  color: #25d366;
}

.social-icon.github {
  color: var(--preto);
}

.social-icon.instagram {
  color: #e1306c;
}

/* Entrada Animations */
@keyframes logoSlideIn {
  from {
    opacity: 0;
    transform: translateX(-30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes arrowFadeIn {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes socialIconsSlideIn {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes socialIconBounce {
  from {
    opacity: 0;
    transform: scale(0.3);
  }
  50% {
    opacity: 1;
    transform: scale(1.2);
  }
  70% {
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Menu Arrow Styles */
.menu-arrow {
  background: var(--transparente);
  border: none;
  color: var(--primaria);
  cursor: pointer;
  padding: var(--espaco-xp);
  border-radius: var(--radius-total);
  transition: var(--transicao-media);
  display: flex;
  align-items: center;
  animation: arrowFadeIn 0.8s ease-out 0.8s both;
}

.menu-arrow.open {
  transform: rotate(180deg);
  animation: arrowFadeIn 0.8s ease-out 0.8s both;
}

.menu-arrow:hover {
  background: var(--preto-transparente);
  transform: scale(1.1);
}

.navigation-menu {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: var(--preto);
  backdrop-filter: blur(10px);
  border-radius: 0 0 var(--radius-grande) var(--radius-grande);
  padding: var(--espaco-2xg) 0;
}

.menu-items {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  gap: var(--espaco-3xg);
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--espaco-2xg);
}

.menu-item {
  opacity: 0;
  transform: translateX(-50px);
  animation: slideInFromLeft 0.6s ease-out forwards;
}

.menu-item a {
  color: var(--branco);
  text-decoration: none;
  font-size: var(--fonte-g);
  font-weight: var(--peso-medio);
  padding: var(--espaco-m) var(--espaco-xg);
  border-radius: var(--radius);
  transition: var(--transicao-media);
  display: block;
}

.menu-item a:hover {
  background: linear-gradient(45deg, var(--secundaria), var(--secundaria-hover));
  transform: translateY(-2px);
  box-shadow: var(--sombra-media);
}

/* Vue Transitions */
.fade-menu-enter-active {
  animation: fadeInMenu 0.5s ease-out;
}

.fade-menu-leave-active {
  animation: fadeOutMenu 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}

.fade-menu-enter-from,
.fade-menu-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}


@keyframes fadeInMenu {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeOutMenu {
  from {
    opacity: 1;
    transform: translateY(0);
  }
  to {
    opacity: 0;
    transform: translateY(-15px);
  }
}

@keyframes slideInFromLeft {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideOutToLeft {
  from {
    opacity: 1;
    transform: translateX(0);
  }
  to {
    opacity: 0;
    transform: translateX(-40px);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .menu-items {
    flex-direction: column;
    gap: var(--espaco-m);
    align-items: center;
  }
  
  .menu-item {
    width: 100%;
    text-align: center;
  }
}

</style>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    scrollToSection(event) {
      event.preventDefault()
      const targetId = event.target.getAttribute('href')
      const targetElement = document.querySelector(targetId)
      
      if (targetElement) {
        // Offset da navbar fixa + espaçamento adicional
        const navbarHeight = 80 // altura aproximada da navbar
        const extraOffset = 60 // espaçamento adicional para compensar o margin-bottom do AboutMe
        const offset = navbarHeight + extraOffset
        
        const targetPosition = targetElement.offsetTop - offset
        
        window.scrollTo({
          top: targetPosition,
          behavior: 'smooth'
        })
        
        // Fecha o menu após clicar
        this.isMenuOpen = false
      }
    }
  }
}
</script>