<template>
  <div class="container-tech" id="tecnologias">
    <div class="title">Tecnologias</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="technologies">
      <div class="tech">HTML5  </div>
      <div class="tech"> CSS3 </div>
      <div class="tech"> JavaScript </div>
      <div class="tech"> Vue </div>
      <div class="tech"> Node </div>
      <div class="tech"> PHP </div>
      <div class="tech"> Laravel </div>
      <div class="tech"> Livewire </div>
      <div class="tech"> Bootstrap </div>
      <div class="tech"> Tailwind </div>
      <div class="tech"> Docker </div>
      <div class="tech"> GIT </div>
      <div class="tech"> GitHub </div>
      <div class="tech"> Figma </div>
      <div class="tech"> MySQL </div>
      <div class="tech"> Mongo </div>
      <div class="tech"> Example </div>
      <div class="tech"> Example </div>
    </div>
  </div>
</template>
<script>
export default {
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
  flex: 1 0 calc(10% - 20px); /* Divide em 10 filhos por linha */
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

</style>
