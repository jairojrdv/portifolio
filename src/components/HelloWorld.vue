<script setup>

import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <div class="container-head" id="home">
    <div class="container-text">
      <div class="header-text">Olá mundo,
      </div>
      <div class="header-text2">meu nome é<mark>Jairo</mark> 
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
  height: 60vh;
  justify-content: space-between;
  align-items: center;
  margin: 30px 0 auto;
  gap: 100px;
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
  width: 580px;
  flex-direction: column;
  align-items: center; /* Centraliza verticalmente o conteúdo */
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
  font-weight: bold;
  font-size: 60px;
  text-align: start;
}
.header-text2 {
  font-weight: bold;
  line-height: 70px;
  font-size: 60px;
  text-align: start;
  margin-top: -6%;
}

.header-text2 mark {
  margin-left: 15px;
  color: #047ade;
  font-size: 80px;
  background: none;
}

.sub-header {
  text-align: start;
  margin-top: 30px;
  font-weight: 400;
  font-size: 30px;
}

@media screen and (max-width: 1080px) {
  .container-text {
    width: 100%;
  }
  .sub-header {
    margin-top: 10px;
    font-size: 22px;
  }
  .profile-img {
    display: none;
  }
}

@media screen and (max-width: 740px) {
  .sub-header {
    margin-top: 3px;
    font-size: 18px;
  }
  .header-text, .header-text2 {
    font-size: 35px;
    line-height: 50px;
  }
  .header-text2 mark {
    font-size: 40px;
    margin-left: 10px;
  }
}
</style>
