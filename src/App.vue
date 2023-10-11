<template>
  <div class="container">
    <NavBar class="NavBar" @openModal="changeModal()"></NavBar>
    <HelloWorld></HelloWorld>
    <AllTechnologies class="surge-effect"></AllTechnologies>
    <SomeProjects class="surge-effect"></SomeProjects>
    <AboutMe></AboutMe>
    <SomeTestimonials></SomeTestimonials>
    
    <FooterCta></FooterCta>
    <a
      href="https://wa.me/5599984311884?text=Ol%C3%A1,%20gostaria%20dei%20uma%20olhada%20no%20seu%20portif%C3%B3lio,%20que%20tal%20uma%20conversa%20sobre%20um%20projeto?"
      target="_blank"
      class="fixed-button"
      v-show="showButton"
      @click="scrollToTop"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="50" height="50" viewBox="0 0 256 258"><defs><linearGradient id="logosWhatsappIcon0" x1="50%" x2="50%" y1="100%" y2="0%"><stop offset="0%" stop-color="#1FAF38"/><stop offset="100%" stop-color="#60D669"/></linearGradient><linearGradient id="logosWhatsappIcon1" x1="50%" x2="50%" y1="100%" y2="0%"><stop offset="0%" stop-color="#F9F9F9"/><stop offset="100%" stop-color="#FFF"/></linearGradient></defs><path fill="url(#logosWhatsappIcon0)" d="M5.463 127.456c-.006 21.677 5.658 42.843 16.428 61.499L4.433 252.697l65.232-17.104a122.994 122.994 0 0 0 58.8 14.97h.054c67.815 0 123.018-55.183 123.047-123.01c.013-32.867-12.775-63.773-36.009-87.025c-23.23-23.25-54.125-36.061-87.043-36.076c-67.823 0-123.022 55.18-123.05 123.004"/><path fill="url(#logosWhatsappIcon1)" d="M1.07 127.416c-.007 22.457 5.86 44.38 17.014 63.704L0 257.147l67.571-17.717c18.618 10.151 39.58 15.503 60.91 15.511h.055c70.248 0 127.434-57.168 127.464-127.423c.012-34.048-13.236-66.065-37.3-90.15C194.633 13.286 162.633.014 128.536 0C58.276 0 1.099 57.16 1.071 127.416Zm40.24 60.376l-2.523-4.005c-10.606-16.864-16.204-36.352-16.196-56.363C22.614 69.029 70.138 21.52 128.576 21.52c28.3.012 54.896 11.044 74.9 31.06c20.003 20.018 31.01 46.628 31.003 74.93c-.026 58.395-47.551 105.91-105.943 105.91h-.042c-19.013-.01-37.66-5.116-53.922-14.765l-3.87-2.295l-40.098 10.513l10.706-39.082Z"/><path fill="#FFF" d="M96.678 74.148c-2.386-5.303-4.897-5.41-7.166-5.503c-1.858-.08-3.982-.074-6.104-.074c-2.124 0-5.575.799-8.492 3.984c-2.92 3.188-11.148 10.892-11.148 26.561c0 15.67 11.413 30.813 13.004 32.94c1.593 2.123 22.033 35.307 54.405 48.073c26.904 10.609 32.379 8.499 38.218 7.967c5.84-.53 18.844-7.702 21.497-15.139c2.655-7.436 2.655-13.81 1.859-15.142c-.796-1.327-2.92-2.124-6.105-3.716c-3.186-1.593-18.844-9.298-21.763-10.361c-2.92-1.062-5.043-1.592-7.167 1.597c-2.124 3.184-8.223 10.356-10.082 12.48c-1.857 2.129-3.716 2.394-6.9.801c-3.187-1.598-13.444-4.957-25.613-15.806c-9.468-8.442-15.86-18.867-17.718-22.056c-1.858-3.184-.199-4.91 1.398-6.497c1.431-1.427 3.186-3.719 4.78-5.578c1.588-1.86 2.118-3.187 3.18-5.311c1.063-2.126.531-3.986-.264-5.579c-.798-1.593-6.987-17.343-9.819-23.64"/></svg>
    </a>
    <div class="modal-content" v-if="showModal">
      <div class="modal" v-if="showModal">
        <div class="input-modal">
          <button class="close" @click="changeModal()">X</button>
          <h2 id="title-modal">Que tal um Email?</h2>
          <form id="myForm" @submit.prevent="sendEmail">
            <div class="row-name">
              <input class="input" type="text" v-model="formData.name" name="name" placeholder="Nome">
              <input class="input" type="email" v-model="formData.email" name="email" placeholder="Email">
            </div>
            <div class="col-send">
              <textarea class="input-text" v-model="formData.message" name="message" placeholder="Mensagem"></textarea>
              <input id="submit" type="submit" value="Enviar">
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import AllTechnologies from "./components/AllTechnologies.vue";
import SomeProjects from "./components/SomeProjects.vue";
import AboutMe from "./components/AboutMe.vue";
import SomeTestimonials from "./components/SomeTestimonials.vue";
import FooterCta from "./components/FooterCta.vue";
import NavBar from "./components/NavBar.vue";
import emailjs from '@emailjs/browser';
// import { ref, onMounted, onUnmounted } from "vue";

export default {
  components: {
    HelloWorld,
    AllTechnologies,
    SomeProjects,
    AboutMe,
    SomeTestimonials,
    FooterCta,
    NavBar
  },
  data() {
    return {
      showButton: false,
      isNavBarTransparent: true,
      showModal: false,
      formData: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollY = window.scrollY;
      this.showButton = scrollY > 0;
      this.isNavBarTransparent = scrollY < 50;
    },
    changeModal() {
      this.showModal = !this.showModal;
      if (this.showModal) {
        document.documentElement.style.overflow = "hidden";
      } else {
        document.documentElement.style.overflow = "auto";
      }
    },
    sendEmail() {
  const form = document.getElementById('myForm'); // Substitua 'myForm' pelo ID do seu formulário
  emailjs.sendForm('service_g13k09o', 'template_vbxhpgt', form, 'qF799MNIDsgfnlHAh')
    .then((result) => {
      alert("Mensagem enviada com sucesso!");
      this.formData.name = '';
      this.formData.email = '';
      this.formData.message = '';
      this.showModal = false;
    })
    .catch((error) => {
      alert("Erro ao enviar a mensagem: " + error.text);
    });
}

  },
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100vw;
  max-width: 100%;
  padding: 0 10px;
}
body .modal-content {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 9998;
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  z-index: 9999;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  gap: 10%;
  align-items: center;
  border-radius: 15px;
  width: 40vw;
  height: 50vh;
}
.row-name{
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  gap: 1vw;
  margin-bottom: 3vh;
}
.col-send{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1vw;
}
.input-modal{
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.input{
  width: 100%;
  height: 100%;
  color: #2c465c;
    font-size: inherit;
    font-family: inherit;
    background-color: transparent;
    padding: 0.7em;
    border: 1px solid #C0C8CE;
    border-radius: 8px;
}
.input-text{
    color: #2c465c;
    font-size: inherit;
    font-family: inherit;
    background-color: transparent;
    padding: 0.7em;
    border: 1px solid #C0C8CE;
    border-radius: 8px;
    min-width: 240px;
    width: 94%!important;
    max-width: 57vw;
    min-height: 80px;
    max-height: 80px;
}
input:focus {
  border-color: 1px solid #2c465c !important;
}
#submit{
  border: 2px solid #2c465c;
	background-color: rgb(224, 238, 255);
	color: #2c465c;
	border-radius: 2rem;
	padding: calc(0.5rem + 0.2vmin) 0;
	width: calc(7rem + 5vmin);
	text-align: center;
	transition: background-color 0.3s, transform 0.3s;
	cursor: pointer;
	margin-bottom: calc(1.4rem + 1vmin);
}
#submit:hover{
  transition: background-color 0.3s, transform 0.3s;
	background-color: rgb(255, 255, 255);
	transform: rotate(5deg);
}
#title-modal{
  font-size: 30px;
}
/* Estilos para o botão de fechar o modal */
.close {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
}
.surge-effect {
  animation: allTech 2s ease-out forwards;
  transform: translateY(100vh);
}
@keyframes allTech {
  from {
    transform: translateY(100vh);
  }
  to {
    transform: translateX(0);
  }
}
.fixed-button {
  position: fixed;
  bottom: 5%;
  right: 3%;
  cursor: pointer;
  transition: opacity 0.3s;
}

/* Aplique um estilo diferente quando o botão estiver visível */
.fixed-button[aria-hidden="false"] {
  opacity: 1;
}

/* Estilo da NavBar fixa no topo */
.NavBar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #f5f5f5; /* Cor de fundo da NavBar */
  z-index: 1000; /* Certifique-se de que a NavBar esteja acima de outros elementos */
  /* Adicione outros estilos de acordo com sua preferência */
  transition: background-color 0.3s, opacity 0.3s;
}

/* Estilo da NavBar transparente */
.NavBar.transparent {
  background-color: rgba(245, 245, 245, 0.8); /* Cor de fundo transparente */
  opacity: 0.8; /* Opacidade quando transparente */
}

/* Estilo para a lista de links */
.section-links {
  list-style: none;
  text-align: center;
  margin-top: 20px; /* Ajuste o espaçamento superior conforme necessário */
}

.section-links li {
  display: inline;
  margin: 0 10px; /* Espaçamento entre os links */
}

.section-links a {
  text-decoration: none;
  color: #333; /* Cor dos links */
  font-weight: bold;
  transition: color 0.3s;
}

.section-links a:hover {
  color: #007bff; /* Cor ao passar o mouse sobre os links */
}
@media screen and (max-width: 540px) {
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow-x: hidden;
  }
  .input-modal #myForm{
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    z-index: 9999;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    gap: 10%;
    align-items: center;
    border-radius: 15px;
    width: 60vw;
    height: 40vh;
  }
  .row-name{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: .8vh;
  }
  .col-send{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 3vh  ;
  }
  #submit{
    border: 2px solid #2c465c;
    background-color: rgb(224, 238, 255);
    color: #2c465c;
    border-radius: 2rem;
    padding: calc(0.5rem + 0.2vmin) 0;
    width: calc(7rem + 5vmin);
    text-align: center;
    transition: background-color 0.3s, transform 0.3s;
    cursor: pointer;
    margin-bottom: calc(1.4rem + 1vmin);
  }
  #submit:hover{
    transition: background-color 0.3s, transform 0.3s;
    background-color: rgb(255, 255, 255);
    transform: rotate(5deg);
  }
  #title-modal{
    font-size: 20px;
  }
  .row-name .input{
    color: #fff;
      font-size: inherit;
      font-family: inherit;
      background-color: transparent;
      padding: 0.7em;
      border: 1px solid #C0C8CE;
      border-radius: 8px;
  }
  .input-text{
    color: #fff;
    font-size: inherit;
    font-family: inherit;
    background-color: transparent;
    padding: 0.7em;
    border: 1px solid #C0C8CE;
    border-radius: 8px;
    min-width: 195px;
    width: 94%!important;
    max-width: 57vw;
    min-height: 30px;
    max-height: 80px;
}
.input-modal{
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
}
</style>
