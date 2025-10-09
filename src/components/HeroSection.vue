<template>
  <section class="hero-section">
    <div class="hero-container">
      <div class="hero-content">
        <div class="hero-text">
          <p class="greeting">Olá, eu sou</p>
          <h1 class="name">Samuel Abreu</h1>
          <h2 class="title">Desenvolvedor <span class="highlight">Full Stack</span></h2>
          <p class="description">
            De Bahia, Brasil
          </p>
          <div class="hero-buttons">
            <button class="btn-primary">Precisa de uma solução?</button>
            <button class="btn-secondary">Mais detalhes</button>
          </div>
        </div>
        <div class="hero-image">
          <div class="image-placeholder">
            <div class="geometric-shapes">
              <div class="shape shape-1"></div>
              <div class="shape shape-2"></div>
              <div class="shape shape-3"></div>
              <div class="shape shape-4"></div>
            </div>
            <div class="profile-image">
              <!-- Placeholder para sua foto -->
              <img src="/profile-placeholder.jpg" alt="Profile" class="profile-img" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
}
</script>

<style scoped>
.hero-section {
  min-height: calc(100vh - 60px);
  background: var(--fundo-dia);
  display: flex;
  align-items: center;
  padding: var(--espaco-m) 0;
  position: relative;
  overflow: hidden;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--espaco-2xg);
  width: 100%;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--espaco-3xg);
  align-items: center;
  min-height: 70vh;
}

.hero-text {
  animation: slideInLeft 1s ease-out;
}

.greeting {
  font-size: var(--fonte-g);
  color: var(--cinza);
  margin-bottom: var(--espaco-p);
  font-weight: var(--peso-normal);
}

.name {
  font-size: clamp(3rem, 8vw, 6rem);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-p);
  line-height: 1.1;
}

.title {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: var(--peso-medio);
  color: var(--preto);
  margin-bottom: var(--espaco-xg);
  line-height: 1.2;
}

.highlight {
  color: var(--secundaria);
  position: relative;
}

.description {
  font-size: var(--fonte-g);
  color: var(--cinza);
  margin-bottom: var(--espaco-2xg);
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: var(--espaco-g);
  flex-wrap: wrap;
}

.btn-primary, .btn-secondary {
  padding: var(--espaco-m) var(--espaco-2xg);
  border-radius: var(--radius);
  font-size: var(--fonte-m);
  font-weight: var(--peso-medio);
  cursor: pointer;
  transition: var(--transicao-media);
  border: none;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: var(--espaco-xp);
}

.btn-primary {
  background: var(--secundaria);
  color: var(--branco);
}

.btn-primary:hover {
  background: var(--secundaria-hover);
  transform: translateY(-2px);
  box-shadow: var(--sombra-media);
}

.btn-secondary {
  background: transparent;
  color: var(--primaria);
  border: 1px solid var(--primaria);
}

.btn-secondary:hover {
  background: var(--primaria);
  color: var(--branco);
  transform: translateY(-2px);
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: slideInRight 1s ease-out;
}

.image-placeholder {
  position: relative;
  width: 400px;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.geometric-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
}

.shape {
  position: absolute;
  background: var(--secundaria);
  border-radius: var(--radius);
}

.shape-1 {
  width: 80px;
  height: 80px;
  top: 10%;
  right: 10%;
  animation: float 3s ease-in-out infinite;
}

.shape-2 {
  width: 60px;
  height: 60px;
  bottom: 20%;
  left: 5%;
  animation: float 3s ease-in-out infinite 1s;
}

.shape-3 {
  width: 40px;
  height: 40px;
  top: 30%;
  left: 15%;
  animation: float 3s ease-in-out infinite 2s;
}

.shape-4 {
  width: 100px;
  height: 50px;
  bottom: 10%;
  right: 20%;
  animation: float 3s ease-in-out infinite 0.5s;
}

.profile-image {
  width: 300px;
  height: 400px;
  border-radius: var(--radius-grande);
  overflow: hidden;
  position: relative;
  z-index: var(--z-cima);
  background: var(--cinza-transparente);
  display: flex;
  align-items: center;
  justify-content: center;
}

.profile-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: var(--radius-grande);
}

/* Animations */
@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: var(--espaco-2xg);
    text-align: center;
  }
  
  .hero-image {
    order: -1;
  }
  
  .image-placeholder {
    width: 300px;
    height: 400px;
  }
  
  .profile-image {
    width: 250px;
    height: 320px;
  }
  
  .hero-buttons {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .hero-section {
    padding: var(--espaco-g) 0;
  }
  
  .image-placeholder {
    width: 250px;
    height: 320px;
  }
  
  .profile-image {
    width: 200px;
    height: 260px;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-primary, .btn-secondary {
    width: 100%;
    max-width: 250px;
    justify-content: center;
  }
}
</style>
