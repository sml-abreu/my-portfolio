<template>
  <section id="sobre" class="about-section">
    <div class="about-container">
      <div class="section-header">
        <h2 class="section-title">Sobre Mim</h2>
      </div>
      
      <div class="about-content">
        <div class="about-image">
          <div class="image-container">
            <img src="/about-photo.jpg" alt="Sobre mim" class="about-photo" />
            <div class="image-decoration">
              <div class="decoration-shape decoration-1"></div>
              <div class="decoration-shape decoration-2"></div>
            </div>
          </div>
        </div>
        
        <div class="about-text">
          <h3 class="about-subtitle">Eu sou <span class="highlight">Samuel Abreu</span></h3>
          <h4 class="about-role">Desenvolvedor Web</h4>
          <p class="about-location">De Bahia, Brasil</p>
          
          <div class="about-description">
            <p>
              Olá! Meu nome é Samuel Abreu e sou desenvolvedor web Full Stack, busco sempre unir design moderno e funcionalidade para entregar experiências digitais completas.
            </p>
            <p>
              Com mais de 2 anos de experiência como desenvolvedor profissional, meus principais diferenciais são a criatividade no desenvolvimento, a criação de visuais atraentes e a construção de layouts totalmente responsivos.
            </p>
          </div>
          
          <div class="about-stats">
            <div class="stat-item">
              <span class="stat-number">2+</span>
              <span class="stat-label">Projetos Concluídos</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">2+</span>
              <span class="stat-label">Anos de Experiência</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">2+</span>
              <span class="stat-label">Clientes Satisfeitos</span>
            </div>
          </div>
          
          <div class="about-actions">
            <button class="btn-download">
              <i class="fas fa-download"></i>
              Download CV
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutMe'
}
</script>

<style scoped>
.about-section {
  padding: var(--espaco-2xg) 0;
  background: var(--branco);
  position: relative;
}

.about-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--espaco-2xg);
}

.section-header {
  text-align: center;
  margin-bottom: var(--espaco-2xg);
}

.section-title {
  font-size: var(--fonte-3xg);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  position: relative;
  display: inline-block;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: var(--secundaria);
  border-radius: var(--radius-pequeno);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: var(--espaco-3xg);
  align-items: center;
}

.about-image {
  position: relative;
  display: flex;
  justify-content: center;
}

.image-container {
  position: relative;
  width: 350px;
  height: 450px;
}

.about-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: var(--radius-grande);
  box-shadow: var(--sombra-pesada);
  position: relative;
  z-index: var(--z-cima);
}

.image-decoration {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.decoration-shape {
  position: absolute;
  background: var(--secundaria);
  border-radius: var(--radius);
}

.decoration-1 {
  width: 80px;
  height: 80px;
  top: -20px;
  right: -20px;
  animation: float 3s ease-in-out infinite;
}

.decoration-2 {
  width: 60px;
  height: 60px;
  bottom: -15px;
  left: -15px;
  animation: float 3s ease-in-out infinite 1.5s;
}

.about-text {
  animation: slideInRight 1s ease-out;
}

.about-subtitle {
  font-size: var(--fonte-2xg);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-p);
}

.highlight {
  color: var(--secundaria);
}

.about-role {
  font-size: var(--fonte-xg);
  font-weight: var(--peso-medio);
  color: var(--preto);
  margin-bottom: var(--espaco-2xg);
}

.about-location {
  font-size: var(--fonte-m);
  color: var(--cinza);
  margin-bottom: var(--espaco-xg);
}

.about-description {
  margin-bottom: var(--espaco-2xg);
}

.about-description p {
  font-size: var(--fonte-m);
  line-height: 1.7;
  color: var(--cinza);
  margin-bottom: var(--espaco-m);
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--espaco-g);
  margin-bottom: var(--espaco-2xg);
  padding: var(--espaco-xg) 0;
  border-top: 1px solid var(--borda);
  border-bottom: 1px solid var(--borda);
}

.stat-item {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: var(--fonte-2xg);
  font-weight: var(--peso-negrito);
  color: var(--secundaria);
  margin-bottom: var(--espaco-xp);
}

.stat-label {
  font-size: var(--fonte-p);
  color: var(--cinza);
  font-weight: var(--peso-medio);
}

.about-actions {
  display: flex;
  gap: var(--espaco-g);
}

.btn-download {
  background: var(--secundaria);
  color: var(--branco);
  padding: var(--espaco-m) var(--espaco-2xg);
  border: none;
  border-radius: var(--radius);
  font-size: var(--fonte-m);
  font-weight: var(--peso-medio);
  cursor: pointer;
  transition: var(--transicao-media);
  display: flex;
  align-items: center;
  gap: var(--espaco-xp);
}

.btn-download:hover {
  background: var(--secundaria-hover);
  transform: translateY(-2px);
  box-shadow: var(--sombra-media);
}

/* Animations */
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
    transform: translateY(-15px);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: var(--espaco-2xg);
    text-align: center;
  }
  
  .image-container {
    width: 280px;
    height: 360px;
  }
  
  .about-stats {
    grid-template-columns: 1fr;
    gap: var(--espaco-m);
  }
  
  .about-actions {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: var(--fonte-2xg);
  }
  
  .image-container {
    width: 250px;
    height: 320px;
  }
  
  .about-subtitle {
    font-size: var(--fonte-xg);
  }
  
  .btn-download {
    width: 100%;
    justify-content: center;
  }
}
</style>
