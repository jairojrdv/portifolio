<template>
  <div class="container-tech" id="tecnologias">
    <div class="title">Tecnologias</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="technologies">
      <div v-for="(technology, index) in technologies" :key="index" class="tech">
        {{ technology.label }}
        <span class="tooltiptext">{{ technology.description }}</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    data(){
      return {
        technologies: [
        { label: "HTML5", description: "Linguagem de marcação para páginas web" },
        { label: "CSS3", description: "Linguagem de estilo para páginas web" },
        { label: "JavaScript", description: "Linguagem de programação para páginas web" },
        { label: "Vue", description: "Framework JavaScript progressivo" },
        { label: "Node", description: "Plataforma que permite a execução de JavaScript no servidor." },
        { label: "PHP", description: "Linguagem de script do lado do servidor" },
        { label: "Laravel", description: "Framework PHP para desenvolvimento web" },
        { label: "Bootstrap", description: "Framework CSS para design responsivo" },
        { label: "Tailwind", description: "Framework CSS utilitário" },
        { label: "Docker", description: "Plataforma de contêinerização" },
        { label: "GIT", description: "Sistema de controle de versão distribuído" },
        { label: "GitHub", description: "Plataforma de hospedagem de código" },
        { label: "Figma", description: "Ferramenta de design de interface de usuário" },
        { label: "MySQL", description: "Sistema de gerenciamento de banco de dados" },
        { label: "Mongo", description: "Banco de dados NoSQL" },
        { label: "PostgreSQL", description: "Sistema de gerenciamento de banco de dados relacional" },
      ],
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
.tech .tooltiptext {
  visibility: hidden;
  width: 160px;
  background-color: #333;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px;
  position: absolute;
  z-index: 1;
  bottom: 125%;
  left: 50%;
  margin-left: -80px;
  opacity: 0;
  transition: opacity 0.3s;
}

.tech:hover .tooltiptext {
  visibility: visible;
  opacity: 1;
}

.tech:hover {
  color: #000000;
  background: #047ade;
  transform: translateY(-3px);
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
