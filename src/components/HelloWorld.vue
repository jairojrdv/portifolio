<script setup>

import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <div class="container-head" id="home">
    <div class="container-text">
      <div class="header-text">Olá mundo,
      </div>
      <div class="header-text2"> meu nome é<mark> Jairo</mark> 
      </div>
      <div class="sub-header">Desenvolvedor Full-Stack</div>
    </div>
    <div class="profile-img">
      <img src="../assets/code-typing-animate.svg" alt="Descrição da imagem">
    </div>
  </div>
</template>

<style scoped>
.container-head {
  text-align: start;
  display: flex;
  width: 90%;
  height: 60vh;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
  margin-top: 6%;
  margin-bottom: 3%;
  gap: 2%;
}

.profile-img {
  width: 375px;
  height: 375px;
  overflow: hidden;
  border-radius: 10px;
  position: relative;
  animation: textImg 2s ease-out forwards;
  transform: translateX(100vw);
}
@keyframes textImg {
  from {
    transform: translateX(100vw);
	}
	to {
		transform: translateX(0);
	}
}

.container-text {
  flex-direction: column;
  align-items: center; /* Centraliza verticalmente o conteúdo */
  width: 48%;
  animation: textFade 2s ease-out forwards;
  transform: translateX(-100vw);
}
@keyframes textFade {
  from {
    transform: translateX(-100vw);
	}
	to {
		transform: translateX(0);
	}
}

.header-text {
  display: flex;
  align-items: top;
  height: 20%;
  font-weight: bold;
  font-size: 70px;
  text-align: start;
}
.header-text2 {
  display: flex;
  align-items: first baseline;
  width: 100%;
  height: 20%;
  font-weight: bold;
  font-size: 70px;
  text-align: start;
  margin-top: -6%;
}

.sub-header {
  text-align: start;
  margin-top: 50px;
  font-weight: 400;
  font-size: 30px;
}
@media screen and (max-width: 768px) {

  .container-head {
    text-align: center;
    display: flex;
    width: 90%;
    height: 60vh;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
    margin-top: 6%;
    margin-bottom: 3%;
  }  .header-text {
    font-size: 30px;
  }

  .sub-header {
    font-size: 16px;
    margin-top: 10px;
  }
  img{
    display: none;
  }
}
mark{
  font-size: 130%;
  color: #047ade;
  background: none;
  margin-left: 2%;
  margin-bottom: 2%;
}
</style>
