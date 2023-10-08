<template>
  <div class="project-container" id="projetos">
    <div class="title">Projetos</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="projects">
      <div class="project">
        <div class="computer">
          <img
            src="../assets/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
        <div class="project-body">
          <div class="project-title">Aprende JS</div>
          <div class="project-description">
            It is a long established fact that a reader will be distracted by the
            readable content of a page when looking at its layout. The point of
            using Lorem Ipsum is that it has a more-or-less normal distribution of
            letters, as opposed to using 'Content here, content here', making it
            look like readable English.
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
          <img
            src="../assets/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
        <div class="project-body">
          <div class="project-title">Check-in System</div>
          <div class="project-description">
            It is a long established fact that a reader will be distracted by the
            readable content of a page when looking at its layout. The point of
            using Lorem Ipsum is that it has a more-or-less normal distribution of
            letters, as opposed to using 'Content here, content here', making it
            look like readable English.
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
          <img
            src="../assets/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
        <div class="project-body">
          <div class="project-title">Aprende JS</div>
          <div class="project-description">
            It is a long established fact that a reader will be distracted by the
            readable content of a page when looking at its layout. The point of
            using Lorem Ipsum is that it has a more-or-less normal distribution of
            letters, as opposed to using 'Content here, content here', making it
            look like readable English.
          </div>
          <div class="used-technologies">
            <div class="tech">JavaScript</div>
            <div class="tech">Node</div>
            <div class="tech">Mongo</div>
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
}

.blue-line-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: -20px;
}

.blue-line {
	height: 0.3rem;
	width: 6rem;
	background-color: #2c465c;
	margin-bottom: calc(3rem + 2vmin);
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
  .project .computer {
    width: 330px;
  }

  .project-body {
    width: 330px;
  }
}
</style>
