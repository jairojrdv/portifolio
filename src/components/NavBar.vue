<template>
  <div class="nav-container">
    <div class="icon-nav">
      <svg width="100" height="100" viewBox="0 0 131 70" fill="whitesmoke" xmlns="http://www.w3.org/2000/svg">
        <path class="shine-top" d="M60.16 43.51C60.16 45.61 59.88 47.5933 59.32 49.46C58.8067 51.3267 57.92 52.96 56.66 54.36C55.4467 55.76 53.86 56.88 51.9 57.72C49.94 58.5133 47.56 58.91 44.76 58.91C41.82 58.91 39.37 58.5367 37.41 57.79C35.45 57.0433 33.7933 56.1333 32.44 55.06L35.73 48.2C36.8967 48.9467 38.18 49.67 39.58 50.37C41.0267 51.07 42.4967 51.42 43.99 51.42C46.23 51.42 48.0267 50.8367 49.38 49.67C50.78 48.4567 51.48 46.24 51.48 43.02V21.81H36.99V14.67H60.16V43.51ZM95.16 43.51C95.16 45.61 94.88 47.5933 94.32 49.46C93.8067 51.3267 92.92 52.96 91.66 54.36C90.4467 55.76 88.86 56.88 86.9 57.72C84.94 58.5133 82.56 58.91 79.76 58.91C76.82 58.91 74.37 58.5367 72.41 57.79C70.45 57.0433 68.7933 56.1333 67.44 55.06L70.73 48.2C71.8967 48.9467 73.18 49.67 74.58 50.37C76.0267 51.07 77.4967 51.42 78.99 51.42C81.23 51.42 83.0267 50.8367 84.38 49.67C85.78 48.4567 86.48 46.24 86.48 43.02V21.81H71.99V14.67H95.16V43.51Z" fill="black"/>
        <path class="shine-top" d="M25.6113 21.2362C25.8146 21.0328 25.976 20.7914 26.086 20.5256C26.1961 20.2599 26.2528 19.9751 26.2528 19.6875C26.2528 19.3998 26.1961 19.115 26.086 18.8493C25.976 18.5835 25.8146 18.3421 25.6113 18.1387C25.4079 17.9353 25.1664 17.774 24.9007 17.6639C24.6349 17.5538 24.3501 17.4972 24.0625 17.4972C23.7749 17.4972 23.4901 17.5538 23.2243 17.6639C22.9586 17.774 22.7171 17.9353 22.5138 18.1387L7.20125 33.4512C6.99754 33.6544 6.83592 33.8958 6.72564 34.1616C6.61536 34.4273 6.55859 34.7122 6.55859 35C6.55859 35.2877 6.61536 35.5726 6.72564 35.8383C6.83592 36.1041 6.99754 36.3455 7.20125 36.5487L22.5138 51.8612C22.9245 52.272 23.4816 52.5027 24.0625 52.5027C24.6434 52.5027 25.2005 52.272 25.6113 51.8612C26.022 51.4504 26.2528 50.8933 26.2528 50.3125C26.2528 49.7316 26.022 49.1745 25.6113 48.7637L11.8431 35L25.6113 21.2362Z" fill="black"/>
        <path class="shine-top" d="M105.389 21.2362C105.185 21.0328 105.024 20.7914 104.914 20.5256C104.804 20.2599 104.747 19.9751 104.747 19.6875C104.747 19.3998 104.804 19.115 104.914 18.8493C105.024 18.5835 105.185 18.3421 105.389 18.1387C105.592 17.9353 105.834 17.774 106.099 17.6639C106.365 17.5538 106.65 17.4972 106.937 17.4972C107.225 17.4972 107.51 17.5538 107.776 17.6639C108.041 17.774 108.283 17.9353 108.486 18.1387L123.799 33.4512C124.002 33.6544 124.164 33.8958 124.274 34.1616C124.385 34.4273 124.441 34.7122 124.441 35C124.441 35.2877 124.385 35.5726 124.274 35.8383C124.164 36.1041 124.002 36.3455 123.799 36.5487L108.486 51.8612C108.075 52.272 107.518 52.5027 106.937 52.5027C106.357 52.5027 105.8 52.272 105.389 51.8612C104.978 51.4504 104.747 50.8933 104.747 50.3125C104.747 49.7316 104.978 49.1745 105.389 48.7637L119.157 35L105.389 21.2362Z" fill="black"/>
        </svg>
    </div>
    <ul class="section-links">
      <li><a href="#home">Home</a></li>
      <li> <a href="#tecnologias">Tecnologias</a></li>
      <li> <a href="#projetos">Projetos</a></li>
      <li> <a href="#sobre">Sobre Mim</a></li>
      <li> <a href="#depoimentos">Depoimentos</a></li>
    </ul>
    <a class="surprise-me-btn" href=" " target="_blank">Contato</a>
  </div>
</template>
<script>
export default {
  methods: {
    scrollToElement(targetId) {
      const targetElement = document.querySelector(targetId);
      if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
      }
    },
  },
};
</script>
<style scoped>
.nav-container{
  height: 80px;
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
.surprise-me-btn {
  margin-right: 70px;
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
.icon-nav{
  margin-left: 100px;
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
  color: #2c465c; /* Cor do texto dos links */
}

.section-links li a:hover {
  color: #047ade; /* Cor do texto dos links ao passar o mouse sobre eles */
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
  }
}
</style>