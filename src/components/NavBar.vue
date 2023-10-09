<template>
  <div>
    <div v-if="menu" class="links-mobile">
      <svg @click="changeMenu()" id="close-menu" width="44" height="44" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M19 6.41L17.59 5L12 10.59L6.41 5L5 6.41L10.59 12L5 17.59L6.41 19L12 13.41L17.59 19L19 17.59L13.41 12L19 6.41Z" fill="#fff"/>
      </svg>
      <ul>
        <li><a href="#home" @click="changeMenu()">Home</a></li>
        <li> <a href="#tecnologias" @click="changeMenu()">Tecnologias</a></li>
        <li> <a href="#projetos" @click="changeMenu()">Projetos</a></li>
        <li> <a href="#sobre" @click="changeMenu()">Sobre Mim</a></li>
        <li> <a href="#depoimentos" @click="changeMenu()">Depoimentos</a></li>
      </ul>
    </div>
    <div v-else class="nav-container">
      <div class="icon-nav">
        <img src="../assets/logo.svg" alt="">
      </div>
      <ul class="section-links">
        <li><a href="#home">Home</a></li>
        <li> <a href="#tecnologias">Tecnologias</a></li>
        <li> <a href="#projetos">Projetos</a></li>
        <li> <a href="#sobre">Sobre Mim</a></li>
        <li> <a href="#depoimentos">Depoimentos</a></li>
      </ul>
      <a class="surprise-me-btn" href="" target="_blank">Contato</a>
      <svg @click="changeMenu()" class="menu-mobile" width="64" height="64" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M3 18V16H21V18H3ZM3 13V11H21V13H3ZM3 8V6H21V8H3Z" fill="#2c465c"/>
      </svg>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menu: false,
    }
  },
  methods: {
    scrollToElement(targetId) {
      const targetElement = document.querySelector(targetId);
      if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
      }
    },
    changeMenu() {
      this.menu = !this.menu
      if (this.menu) {
        document.documentElement.style.overflow = 'hidden';
      } else {
        document.documentElement.style.overflow = 'auto';
      }
    },
  },
};
</script>
<style scoped>
.nav-container{
  height: 80px;
  padding: 0 40px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  animation: nav 2s ease-out forwards;
  transform: translateY(-100vh);
}
@keyframes nav {
  from {
    transform: translateY(-100vh);
	}
	to {
		transform: translateX(0);
	}
}

.menu-mobile {
  display: none;
  cursor: pointer;
}
.surprise-me-btn {
	border: 2px solid #2c465c;
	background-color: rgb(224, 238, 255);
	color: #2c465c;
	border-radius: 2rem;
	padding: calc(0.5rem + 0.2vmin) 0;
	width: calc(7rem + 5vmin);
	text-align: center;
	transition: background-color 0.3s, transform 0.3s;
	cursor: pointer;
  margin-top: 3%;
	margin-bottom: calc(1.4rem + 1vmin);
}

.surprise-me-btn:hover {
	transition: background-color 0.3s, transform 0.3s;
	background-color: rgb(255, 255, 255);
	transform: rotate(5deg);
}
.section-links {
  list-style-type: none; /* Remova os marcadores de lista */
  margin: 0;
  padding: 0;
  display: flex;
  gap: 20px; /* Espaçamento entre os itens da lista */
  cursor: pointer;
}

.section-links li {
  font-size: 18px; /* Tamanho da fonte dos itens da lista */
  font-weight: bold; /* Peso da fonte dos itens da lista */
}

/* Estilize os links de navegação */
.section-links li a {
  text-decoration: none; /* Remova a sublinhado dos links */
  color: #000000; /* Cor do texto dos links */
}

.section-links li a:hover {
  color: #047ade; /* Cor do texto dos links ao passar o mouse sobre eles */
}
.shine-top {
  animation: pulseTop 2s ease-in-out infinite alternate;
}

.links-mobile {
  background: rgba(0, 0, 0, .8);
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}

.links-mobile ul {
  height: 100%;
  list-style-type: none;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
  font-size: 28px;
  margin-left: -28px;
}

#close-menu {
  position: absolute;
  top: 50px;
  cursor: pointer;
}

@keyframes pulseTop {
  0% {
    fill: #2c465c;
  }

  100% {
    fill: #047ade; /* Cor brilhante desejada */
    text-shadow: #047ade 0 0 20px;
  }
}

@media screen and (max-width: 1080px) {
  .section-links {
    display: none;
  }

  .surprise-me-btn {
    display: none;
  }

  .menu-mobile {
    display: block;
  }
}
</style>