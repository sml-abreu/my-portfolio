<template>
  <section id="experiencia" class="experience-section">
    <div class="experience-container">
      <div class="section-header">
        <h2 class="section-title">Experiência</h2>
        <p class="section-subtitle">Minha jornada profissional</p>
      </div>
      
      <div class="experience-content">
        <div class="timeline">
          <div 
            v-for="(item, index) in experiences" 
            :key="item.id"
            class="timeline-item"
            :class="{ 'timeline-item-right': index % 2 === 1 }"
          >
            <div class="timeline-marker">
              <div class="timeline-dot"></div>
            </div>
            <div class="timeline-content">
              <div class="timeline-card">
                <div class="timeline-header">
                  <h3 class="timeline-title">{{ item.position }}</h3>
                  <span class="timeline-company">{{ item.company }}</span>
                  <span class="timeline-period">{{ item.period }}</span>
                </div>
                <div class="timeline-body">
                  <p class="timeline-description">{{ item.description }}</p>
                  <div class="timeline-skills">
                    <span 
                      v-for="skill in item.skills" 
                      :key="skill"
                      class="skill-tag"
                    >
                      {{ skill }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="education-section">
        <h3 class="education-title">Educação & Certificações</h3>
        <div class="education-grid">
          <div 
            v-for="(edu, index) in education" 
            :key="edu.id"
            class="education-card"
            :style="{ animationDelay: (index * 0.2) + 's' }"
          >
            <div class="education-icon">
              <i :class="edu.icon"></i>
            </div>
            <div class="education-content">
              <h4 class="education-course">{{ edu.course }}</h4>
              <p class="education-institution">{{ edu.institution }}</p>
              <span class="education-year">{{ edu.year }}</span>
            </div>
          </div>
        </div>
      </div>
      
    </div>
  </section>
</template>

<script>
export default {
  name: 'Experience',
  data() {
    return {
      experiences: [
        {
          id: 1,
          position: 'Desenvolvedor Frontend',
          company: 'Freelancer',
          period: '2023 - Presente',
          description: 'Desenvolvimento de sites responsivos e aplicações web usando Vue.js, HTML, CSS e JavaScript. Foco em criar interfaces modernas e funcionais.',
          skills: ['Vue.js', 'HTML5', 'CSS3', 'JavaScript', 'Git']
        },
        {
          id: 2,
          position: 'Estudante de Desenvolvimento Web',
          company: 'Autodidata',
          period: '2022 - 2023',
          description: 'Aprendizado intensivo de tecnologias web através de cursos online, projetos pessoais e prática constante. Desenvolvimento de projetos para portfólio.',
          skills: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'Figma']
        }
      ],
      education: [
        {
          id: 1,
          course: 'Desenvolvimento Web Full Stack',
          institution: 'Cursos Online',
          year: '2022 - 2023',
          icon: 'fas fa-code'
        },
        {
          id: 2,
          course: 'JavaScript Moderno',
          institution: 'Udemy',
          year: '2023',
          icon: 'fab fa-js-square'
        },
        {
          id: 3,
          course: 'Vue.js Completo',
          institution: 'Vue School',
          year: '2023',
          icon: 'fab fa-vuejs'
        }
      ]
    }
  }
}
</script>

<style scoped>
.experience-section {
  padding: var(--espaco-2xg) 0;
  background: var(--branco);
  position: relative;
}

.experience-container {
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
  margin-bottom: var(--espaco-m);
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

.section-subtitle {
  font-size: var(--fonte-g);
  color: var(--cinza);
}

.experience-content {
  margin-bottom: var(--espaco-3xg);
}

.timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
}

.timeline::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 100%;
  background: var(--secundaria);
  border-radius: var(--radius-pequeno);
}

.timeline-item {
  position: relative;
  width: 50%;
  padding: var(--espaco-g);
  animation: slideInLeft 0.8s ease-out;
}

.timeline-item-right {
  left: 50%;
  animation: slideInRight 0.8s ease-out;
}

.timeline-marker {
  position: absolute;
  top: var(--espaco-g);
  right: -15px;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.timeline-item-right .timeline-marker {
  left: -15px;
  right: auto;
}

.timeline-dot {
  width: 20px;
  height: 20px;
  background: var(--secundaria);
  border-radius: 50%;
  border: 4px solid var(--branco);
  box-shadow: var(--sombra-media);
}

.timeline-card {
  background: var(--branco);
  border-radius: var(--radius-grande);
  padding: var(--espaco-xg);
  box-shadow: var(--sombra-media);
  border: 1px solid var(--borda);
  transition: var(--transicao-media);
}

.timeline-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--sombra-pesada);
}

.timeline-header {
  margin-bottom: var(--espaco-m);
}

.timeline-title {
  font-size: var(--fonte-g);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-xp);
}

.timeline-company {
  display: block;
  font-size: var(--fonte-m);
  color: var(--secundaria);
  font-weight: var(--peso-medio);
  margin-bottom: var(--espaco-xp);
}

.timeline-period {
  display: inline-block;
  background: var(--secundaria-transparente);
  color: var(--secundaria);
  padding: var(--espaco-xp) var(--espaco-p);
  border-radius: var(--radius-total);
  font-size: var(--fonte-p);
  font-weight: var(--peso-medio);
}

.timeline-description {
  font-size: var(--fonte-m);
  line-height: 1.6;
  color: var(--cinza);
  margin-bottom: var(--espaco-m);
}

.timeline-skills {
  display: flex;
  flex-wrap: wrap;
  gap: var(--espaco-xp);
}

.skill-tag {
  background: var(--primaria-transparente);
  color: var(--primaria);
  padding: var(--espaco-xp) var(--espaco-p);
  border-radius: var(--radius-total);
  font-size: var(--fonte-xp);
  font-weight: var(--peso-medio);
}

.education-section {
  margin-bottom: var(--espaco-3xg);
}

.education-title {
  font-size: var(--fonte-2xg);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  text-align: center;
  margin-bottom: var(--espaco-2xg);
}

.education-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--espaco-g);
}

.education-card {
  background: var(--branco);
  border-radius: var(--radius-grande);
  padding: var(--espaco-xg);
  box-shadow: var(--sombra-media);
  border: 1px solid var(--borda);
  display: flex;
  align-items: center;
  gap: var(--espaco-m);
  transition: var(--transicao-media);
  animation: fadeInUp 0.8s ease-out;
}

.education-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--sombra-pesada);
}

.education-icon {
  width: 60px;
  height: 60px;
  background: var(--secundaria-transparente);
  border-radius: var(--radius-total);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: var(--fonte-xg);
  color: var(--secundaria);
  flex-shrink: 0;
}

.education-course {
  font-size: var(--fonte-m);
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-xp);
}

.education-institution {
  font-size: var(--fonte-p);
  color: var(--cinza);
  margin-bottom: var(--espaco-xp);
}

.education-year {
  font-size: var(--fonte-p);
  color: var(--secundaria);
  font-weight: var(--peso-medio);
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

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounceIn {
  0% {
    opacity: 0;
    transform: scale(0.3);
  }
  50% {
    opacity: 1;
    transform: scale(1.05);
  }
  70% {
    transform: scale(0.9);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .timeline::before {
    left: 30px;
  }
  
  .timeline-item,
  .timeline-item-right {
    width: 100%;
    left: 0;
    padding-left: 70px;
  }
  
  .timeline-marker,
  .timeline-item-right .timeline-marker {
    left: 15px;
    right: auto;
  }
  
  .education-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: var(--fonte-2xg);
  }
  
  .timeline-item,
  .timeline-item-right {
    padding-left: 50px;
  }
  
  .timeline-marker,
  .timeline-item-right .timeline-marker {
    left: 5px;
  }
  
  .education-card {
    flex-direction: column;
    text-align: center;
  }
}
</style>
