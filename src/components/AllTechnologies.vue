<template>
  <div class="container-tech" id="tecnologias">
    <div class="title">Tecnologias</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="technologies">
      <div v-for="(technologie, index) in technologies" :key="index" class="tech">{{ technologie }}</div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return {
      technologies: ["HTML5", "CSS3", "JavaScript", "Vue", "Node", "PHP", "Laravel", "Bootstrap", "Tailwind", "Docker", "GIT", "GitHub", "Figma", "MySQL", "Mongo", "PostgreSQL"]
    }
  },
  mounted() {
    const technologies = document.querySelectorAll('.tech-scroll');

    // Ouvinte de evento de rolagem
    window.addEventListener('scroll', () => {
      const scrollDirection = window.scrollX > 0 ? 'right' : 'left';

      // Adicionar ou remover a classe dependendo da direção da rolagem
      technologies.forEach((tech) => {
        if (scrollDirection === 'right') {
          tech.classList.add('tech-scroll');
        } else {
          tech.classList.remove('tech-scroll');
        }
      });
    });
  },
};
</script>
<style>
.container-tech {
  margin: 0;
  padding: 0;
  margin-top: 2%;
}
.title{
  font-size: 50px;
  font-weight: bold;
  margin-bottom: 2%;
}

.technologies {
  width: 80%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin: 0 auto;
}

.tech {
  flex: 1 0 calc(10% - 10px);
  min-width: 30px;
  margin: 10px; /* Espaçamento entre os filhos */
  border-radius: 5px;
  color: #FFFFFF;
  background: #2c465c;
  padding: 5px;
  cursor: pointer;
  transition: transform 0.3s ease; /* Adiciona uma transição suave */
}

.tech:hover {
  color: #000000;
  background: #047ade;
  transform: translateY(-3px); /* Levanta levemente o elemento */
}

@media screen and (max-width: 540px) {
  .tech {
    flex: 1 0 calc(30% - 5px); /* Divide em 10 filhos por linha */
    min-width: 60px;
    margin: 10px; /* Espaçamento entre os filhos */
    border-radius: 5px;
    color: #FFFFFF;
    background: #2c465c;
    padding: 5px;
    cursor: pointer;
    transition: transform 0.3s ease; /* Adiciona uma transição suave */
  }
}
</style>
