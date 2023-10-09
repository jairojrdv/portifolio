<template>
  <div class="project-container" id="projetos">
    <div class="title">Projetos</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="projects">
      <div class="project">
        <div class="computer">
          <a href="https://jairojrdv.github.io/front-aprende-js/" target="_blank">
            <img
              src="../assets/macbook-white.png"
              alt="MacBook Computer Apple"
            >
            <div id="aprendejs-img">
              <img src="../assets/aprendejs-img.jpg" alt="">
            </div>
          </a>
        </div>
        <div class="project-body">
          <div class="project-title">Aprende JS</div>
          <div class="project-description">
            Aprende JS é uma aplicação full-stack feita para ensinar Javascript através do método de estudo por repetição. Basicamente a aplicação traz o nome de um método javascript, a sua definição e uma aplicação do mesmo.
          </div>
          <div class="used-technologies">
            <div class="tech">JavaScript</div>
            <div class="tech">Node</div>
            <div class="tech">Mongo</div>
          </div>
        </div>
      </div>
      <div class="project reverse">
        <div class="computer">
          <a href="https://encontro-b5uu8cm7b-juliodeveloper.vercel.app/" target="_blank">
            <img
              src="../assets/macbook-white.png"
              alt="MacBook Computer Apple"
            />
            <div id="checkin-img">
              <img src="../assets/checkin-img.png">
            </div>
          </a>
        </div>
        <div class="project-body">
          <div class="project-title">Check-in System</div>
          <div class="project-description">
            O sistema de Check-in foi feito para controlar, gerenciar e organizar com muito mais facilidade os encontros da igreja local que frequento. O sistema basicamente cadastra um "encontrista" com apenas alguns de seus dados e o deixa disponível para o check-in assim que chega para o embarque no dia e horário combinado. Nesta aplicação fui idealizador e responsável pelo front-end.
          </div>
          <div class="used-technologies">
            <div class="tech">Vue</div>
            <div class="tech">Node</div>
            <div class="tech">Mongo</div>
          </div>
        </div>
      </div>
      <div class="project">
        <div class="computer">
          <a href="https://jairojrdv.github.io/joguinho-nonato-bros/" target="_blank">
            <img
              src="../assets/macbook-white.png"
              alt="MacBook Computer Apple"
            />
            <div id="nonatobros-img">
              <img src="../assets/nonatobros-img.png">
            </div>
          </a>
        </div>
        <div class="project-body">
          <div class="project-title">Nonato Bros</div>
          <div class="project-description">
            Nonato Bros é um jogo inspirado em Mario Bros no qual o personagem principal é Raimundo Nonato. O divertido jogo pode facilmente ser jogado no computador porém como ainda está em produção, não está disponível para mobile atualmente.
          </div>
          <div class="used-technologies">
            <div class="tech">JavaScript</div>
            <div class="tech">HTML5</div>
            <div class="tech">CSS3</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
.project-container {
  width: 100vw;
  margin: 80px 0;
}

.projects {
  display: flex;
  flex-flow: column;
  align-items: center;
  gap: 60px;
}

.project {
  width: 100%;
  display: flex;
  align-items: center;
  gap: 20px;
}

.project.reverse {
  flex-direction: row-reverse;
}


.project .computer {
  width: 500px;
  position: relative;
}

.project .computer img {
  width: 100%;
}

.project-body {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 500px;
}

.project-title {
  text-align: start;
  font-size: 25px;
  font-weight: 500;
}

.project.reverse .project-title {
  text-align: end;
}

.project-description {
  text-align: start;
}

.project.reverse .project-description {
  text-align: end;
}

.used-technologies {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.blue-line-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: -15px;
}

.blue-line {
	height: 0.3rem;
	width: 6rem;
	background-color: #2c465c;
	margin-bottom: calc(3rem + 2vmin);
}
#aprendejs-img img{
  position: absolute;
  top: 8%;
  left: 15.8%;
  width: 68%;
  height: 85%;
  z-index: -1;
}
#checkin-img img{
  position: absolute;
  top: 8.1%;
  left: 15%;
  width: 71%;
  height: 79%;
  z-index: -1;
}
#nonatobros-img img{
  position: absolute;
  top: 8.1%;
  left: 16%;
  width: 68%;
  height: 79%;
  z-index: -1;
}

@media screen and (max-width: 1080px) {
  .project, .project.reverse {
    flex-direction: column;
  }

  .project .project-title, .project.reverse .project-title {
    text-align: center;
  }

  .project .project-description, .project.reverse .project-description {
    text-align: center;
  }
}

@media screen and (max-width: 740px) {
  .project-body{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .project .computer {
    width: 330px;
  }

  .project-body {
    width: 330px;
  }
}
</style>
