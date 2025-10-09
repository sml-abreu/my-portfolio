<template>
  <section id="experiencia" class="experience-section">
    <div class="experience-container">
      <div class="section-header">
        <h2 class="section-title">Experiência</h2>
        <p class="section-description">
          Tecnologias e frameworks que domino para criar soluções web completas e modernas
        </p>
      </div>
      
      <div class="experience-list">
        <div 
          v-for="item in experiences" 
          :key="item.id"
          class="experience-item"
        >
          <div class="item-header">
            <div class="item-icon">
              <i :class="item.icon"></i>
            </div>
            <div class="item-info">
              <h4 class="item-title">{{ item.position }}</h4>
              <p class="item-period">{{ item.period }}</p>
            </div>
          </div>
          <div class="item-skills">
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
          position: 'JavaScript',
          period: 'Linguagem Principal',
          icon: 'fab fa-js',
          skills: ['ES6+', 'Async/Await', 'DOM', 'APIs']
        },
        {
          id: 2,
          position: 'Vue.js',
          period: 'Framework Frontend',
          icon: 'fab fa-vuejs',
          skills: ['Components', 'Vue Router', 'Pinia', 'Vite']
        },
        {
          id: 3,
          position: 'React',
          period: 'Biblioteca UI',
          icon: 'fab fa-react',
          skills: ['JSX', 'Hooks', 'Context API', 'Redux']
        },
        {
          id: 4,
          position: 'Node.js',
          period: 'Backend',
          icon: 'fab fa-node-js',
          skills: ['Express', 'REST APIs', 'JWT', 'MongoDB']
        }
      ]
    }
  }
}
</script>

<style scoped>
.experience-section {
  padding: var(--espaco-3xg) 0;
  background: var(--fundo-dia);
  position: relative;
}

.experience-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--espaco-2xg);
}

.section-header {
  text-align: center;
  margin-bottom: var(--espaco-3xg);
}

.section-title {
  font-size: 4rem;
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-2xg);
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

.section-description {
  font-size: 1.25rem;
  color: var(--cinza);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}


.experience-list {
  max-width: 1200px;
  margin: 0 auto;
}

.experience-item {
  background: var(--branco);
  border-radius: var(--radius-grande);
  padding: var(--espaco-g);
  margin-bottom: var(--espaco-m);
  transition: var(--transicao-media);
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.experience-item:hover {
  transform: translateX(4px);
  border-color: rgba(195, 38, 25, 0.2);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
}

.item-header {
  display: flex;
  align-items: center;
  gap: var(--espaco-m);
  margin-bottom: var(--espaco-p);
}

.item-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, var(--secundaria) 0%, #e63946 100%);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: var(--branco);
  flex-shrink: 0;
}
.item-info {
  flex: 1;
}

.item-title {
  font-size: 1.5rem;
  font-weight: var(--peso-negrito);
  color: var(--primaria);
  margin-bottom: var(--espaco-xp);
}

.item-period {
  font-size: 1.1rem;
  color: var(--cinza);
  font-weight: var(--peso-normal);
}

.item-skills {
  display: flex;
  flex-wrap: wrap;
  gap: var(--espaco-xp);
}

.skill-tag {
  background: rgba(33, 40, 50, 0.05);
  color: var(--cinza);
  padding: 6px 12px;
  border-radius: var(--radius-total);
  font-size: 1rem;
  font-weight: var(--peso-normal);
}



/* Responsive Design */

/* Tablet (768px - 1199px) */
@media (max-width: 1199px) and (min-width: 768px) {
  .experience-container {
    padding: 0 var(--espaco-xg);
  }
  
  .experience-list {
    max-width: 900px;
  }
  
  .section-title {
    font-size: var(--fonte-2xg);
  }
  
  .section-description {
    font-size: var(--fonte-m);
  }
}

/* Mobile (até 767px) */
@media (max-width: 767px) {
  .experience-section {
    padding: var(--espaco-xg) 0;
  }
  
  .experience-container {
    padding: 0 var(--espaco-m);
  }
  
  .section-header {
    margin-bottom: var(--espaco-xg);
  }
  
  .section-title {
    font-size: var(--fonte-3xg);
  }
  
  .section-description {
    font-size: var(--fonte-g);
    padding: 0;
  }
  
  .experience-list {
    max-width: 100%;
  }
  
  .experience-item {
    padding: var(--espaco-m);
    margin-bottom: var(--espaco-m);
  }
  
  .item-header {
    gap: var(--espaco-m);
  }
  
  .item-icon {
    width: 60px;
    height: 60px;
    font-size: 2rem;
  }
  
  .item-title {
    font-size: var(--fonte-g);
  }
  
  .item-period {
    font-size: var(--fonte-m);
  }
  
  .item-skills {
    gap: var(--espaco-p);
  }
  
  .skill-tag {
    padding: 8px 14px;
    font-size: var(--fonte-p);
  }
}
</style>
