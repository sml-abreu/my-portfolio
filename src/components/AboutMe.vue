<template>
  <section id="sobre" class="about-section">
    <div class="about-container">
      <div class="section-header">
        <h2 class="section-title">Sobre Mim</h2>
      </div>
      
      <div class="about-content">
        <div class="about-image">
          <img src="/about-photo.jpg" alt="Sobre mim" class="about-photo" />
        </div>
        
        <div class="about-text">
          <h3 class="about-subtitle">Olá, eu sou <span class="highlight">Samuel Abreu</span></h3>
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
  padding: var(--espaco-3xg) 0;
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
  font-size: 4rem;
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
  width: 350px;
  height: 450px;
}

.about-text {
  animation: slideInRight 1s ease-out;
}

.about-subtitle {
  font-size: 2.5rem;
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-p);
}

.highlight {
  color: var(--secundaria);
}

.about-role {
  font-size: 1.75rem;
  font-weight: var(--peso-medio);
  color: var(--preto);
  margin-bottom: var(--espaco-2xg);
}

.about-location {
  font-size: 1.25rem;
  color: var(--cinza);
  margin-bottom: var(--espaco-xg);
}

.about-description {
  margin-bottom: var(--espaco-2xg);
}

.about-description p {
  font-size: 1.25rem;
  line-height: 1.7;
  color: var(--cinza);
  margin-bottom: var(--espaco-m);
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
  font-size: 1.25rem;
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

/* Responsive Design */

/* Tablet (768px - 1199px) */
@media (max-width: 1199px) and (min-width: 768px) {
  .about-container {
    padding: 0 var(--espaco-xg);
  }
  
  .section-title {
    font-size: var(--fonte-2xg);
  }
  
  .about-subtitle {
    font-size: var(--fonte-xg);
  }
}

/* Mobile (até 767px) */
@media (max-width: 767px) {
  .about-section {
    padding: var(--espaco-xg) 0;
  }
  
  .about-container {
    padding: 0 var(--espaco-m);
  }
  
  .section-header {
    margin-bottom: var(--espaco-xg);
  }
  
  .section-title {
    font-size: var(--fonte-3xg);
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: var(--espaco-xg);
    text-align: center;
  }
  
  .about-image {
    width: 280px;
    height: 360px;
    margin: 0 auto;
  }
  
  .about-subtitle {
    font-size: var(--fonte-2xg);
  }
  
  .about-role {
    font-size: var(--fonte-g);
  }
  
  .about-location {
    font-size: var(--fonte-m);
  }
  
  .about-description p {
    font-size: var(--fonte-g);
  }
  
  .btn-download {
    width: 100%;
    justify-content: center;
    font-size: var(--fonte-m);
    padding: var(--espaco-m) var(--espaco-xg);
  }
  
  .about-actions {
    justify-content: center;
  }
}
</style>
