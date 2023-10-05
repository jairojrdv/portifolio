<template>
  <div class="project-container" id="projetos">
    <div class="title">Projetos</div>
    <div class="blue-line-container">
      <div class="blue-line"></div>
    </div>
    <div class="project-1">
      <div class="card">
        <div class="computer">
          <img
            src="https://www.bebold.ch/img/home/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
      </div>
      <div class="project-body-1">
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
    <div class="project-2">
      <div class="project-body-1">
        <div class="project-title-1">Check-in System</div>
        <div class="project-description-1">
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
      <div class="card">
        <div class="computer">
          <img
            src="https://www.bebold.ch/img/home/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
      </div>
    </div>
    <div class="project-3">
      <div class="card">
        <div class="computer">
          <img
            src="https://www.bebold.ch/img/home/macbook-white.png"
            alt="MacBook Computer Apple"
          />
          <div id="" style=""></div>
        </div>
      </div>
      <div class="project-body-1">
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
</template>
<style>
.project-container {
  margin-top: 3%;
}
.project-1 {
  margin-left: 8%;
  width: 950px;
  height: 400px;
  display: flex;
  flex-direction: row;
  gap: 50px;
}
.project-2 {
  margin-left: 28%;
  margin-top: 5%;
  width: 950px;
  height: 400px;
  display: flex;
  flex-direction: row;
  gap: 50px;
}
.project-3 {
  margin-left: 8%;
  margin-top: 5%;
  width: 950px;
  height: 400px;
  display: flex;
  flex-direction: row;
  gap: 50px;
}
.card {
  width: 40%;
  display: flex;
  align-items: center;
  position: relative;
}
.project-body-1 {
  width: 60%;
  height: 80%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.project-body-2 {
  width: 60%;
  height: 80%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.project-title {
  display: flex;
  margin-bottom: 5%;
  font-size: 25px;
  font-weight: 500;
}
.project-title-1 {
  display: flex;
  justify-content: right;
  margin-bottom: 5%;
  font-size: 25px;
  font-weight: 500;
}
.project-description {
  text-align: left;
  margin-bottom: 4%;
}
.project-description-1 {
  text-align: right;
  margin-bottom: 4%;
}
.used-technologies {
  display: flex;
}
.computer {
  position: absolute; /* Posiciona a .computer dentro do container .card */
  top: 40%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  width: 180%;
  opacity: 1;
  z-index: 0;
  transition: all 0.3s ease;
}

.computer img {
  position: absolute;
  top: 35%;
  left: 50%;
  width: 100%;
  height: auto;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  z-index: 1;
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
</style>
