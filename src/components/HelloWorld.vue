<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

<template>
  <div class="container-head" id="home">
    <div class="container-text">
      <div class="header-text">Olá mundo,</div>
      <div class="header-text2">
        meu nome é<mark class="shine-top">Jairo</mark>
      </div>
      <div class="sub-header">Desenvolvedor Full-Stack</div>
    </div>
    <div class="profile-img">
      <img src="../assets/code-typing-animate.svg" alt="Descrição da imagem" />
    </div>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  // Outras opções do componente aqui
}
</script>

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

.shine-top {
  animation: pulseTop 2s ease-in-out infinite alternate;
}
@keyframes pulseTop {
  0% {
    fill: #2c465c;
  }

  100% {
    fill: #047ade; /* Cor brilhante desejada */
    text-shadow: #047ade 0px 0px 3px;
  }
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
  .shine-top {
    animation: pulseTop 2s ease-in-out infinite alternate;
  }
  @keyframes pulseTop {
    0% {
      fill: #2c465c;
    }

    100% {
      fill: #047ade; /* Cor brilhante desejada */
      text-shadow: #047ade 0px 0px 8px;
    }
  }
  .sub-header {
    margin-top: 3px;
    font-size: 18px;
  }
  .header-text,
  .header-text2 {
    font-size: 35px;
    line-height: 50px;
  }
  .header-text2 mark {
    font-size: 40px;
    margin-left: 10px;
  }
  .container-head {
    animation: soft 8s ease-in-out infinite;
    background: #e8ecf0;
    background-position: 50%;
    background-repeat: no-repeat;
    background-size: cover;
    border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
    height: 20rem;
    position: relative;
    transition: all 1s ease-in-out;
    width: 20rem;
    margin: 200px;
  }
  @keyframes soft {
    0% {
      border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
    }

    50% {
      border-radius: 30% 60% 70% 40%/50% 60% 30% 60%;
    }
    100% {
      border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
    }
  }
  .container-text {
    width: 300px;
  }
}
</style>
