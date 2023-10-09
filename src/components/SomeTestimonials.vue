<template>
  <body>
    <div class="content-wrapper" id="depoimentos">
      <h1>Depoimentos</h1>
      <div class="blue-line"></div>
      <div class="wrapper-for-arrows">
        <div style="opacity: 0;" class="chicken"></div>
        <div class="review-wrap">
          <div class="imgDiv" :style="{ '--current-person-photo': currentPerson.photo }"></div>
          <div class="personName">{{ currentPerson.name }}</div>
          <div class="profession">{{ currentPerson.profession }}</div>
          <div class="description">{{ currentPerson.description }}</div>
        </div>
        <a :href="currentPerson.link" class="surprise-me-btn" target="_blank" @click="toggleChicken">Linkedin</a>
        <div class="left-arrow-wrap arrow-wrap">
          <div class="arrow" @click="setNextCard('left')"></div>
        </div>
        <div class="right-arrow-wrap arrow-wrap">
          <div class="arrow" @click="setNextCard('right')"></div>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  data() {
    return {
      currentPersonIndex: 0,
      isChickenVisible: false,
      people: [
				{
					photo:
						"url('https://media.licdn.com/dms/image/C4D03AQFP5ooZ_mGnCQ/profile-displayphoto-shrink_400_400/0/1516955073834?e=1702512000&v=beta&t=0n2lJ2TVlZJRRLqOACXLfLRBCYDoZlCEaWQt5evyQBk')",
					name: "Jairo Rodrigues",
					profession: "CTO Grupo VOZ",
					description:
						"Durante os 9 meses em que Jairo Junior estagiou conosco na área de desenvolvimento de software, ele se destacou de forma notável. Inteligente, ético e com uma capacidade incrível de aprendizado rápido, Jairo não só trouxe competência técnica, mas também uma energia positiva contagiante para a equipe. Foi um privilégio trabalhar ao lado de alguém tão dedicado e talentoso.",
						link: "https://www.linkedin.com/in/jairo-rodrigues-527927130/"
				},
        {
          photo:
            "url('https://media.licdn.com/dms/image/D4D03AQE4t2H0gJGZtg/profile-displayphoto-shrink_400_400/0/1671991801612?e=1701907200&v=beta&t=30D39saxui5BpN0wJ1Hwmle0ILP2efh6UN-tBT34ulg')",
          name: "Ygor Alberto",
          profession: "TECH LEAD DEFENSIVE SECURE",
          description:
            "Jairo é um profissional exemplar onde está sempre em busca de novos aprendizados e desafios. Seu objetivo é sempre baseado no melhor para a empresa e seu crescimento profissional e pessoal. Sabe trabalhar em equipe, comunicativo, comprometido, proativo e didático.",
            link: "https://www.linkedin.com/in/ygoralbert/",
        },
        {
          photo:
            "url('https://media.licdn.com/dms/image/D4D03AQG-K9E7R8okoQ/profile-displayphoto-shrink_400_400/0/1684517946748?e=1702512000&v=beta&t=FxK1uSTwsto2J03h2IgswtIBXFUPmkEGRMT4iEJfof0')",
          name: "Welliton Cunha",
          profession: "Backend Pleno Honda Motoca",
          description:
            "É com grande satisfação que recomendo Jairo Araújo como desenvolvedor de software altamente competente. Durante o seu desempenho na faculdade, demonstrou profundo conhecimento técnico, criatividade e comprometimento com a qualidade. Sua capacidade de solucionar problemas de forma eficaz e trabalhar bem em equipe fazem dele um ativo valioso. Tenho certeza de que Jairo Araújo continuará a ser uma contribuição valiosa para qualquer projeto ou organização.",
						link: "https://www.linkedin.com/in/welliton-cunha-1ab27833/",
        },
        {
          photo:
            "url('https://media.licdn.com/dms/image/D4D03AQGjOzIgHeXYWw/profile-displayphoto-shrink_400_400/0/1686343982695?e=1702512000&v=beta&t=qMrby2W2xBRTrBKSVAy-f8j8JFVMmlcsusAtxFNK9yo')",
          name: "Thalles Canela",
          profession: "Gerente de Projeto Honda Motoca",
          description:
            "Um aluno organizado e dedicado com metas de crescimento bem planejadas.",
						link: "https://www.linkedin.com/in/thalles-canela/"
        },
				{
          photo:
            "url('https://media.licdn.com/dms/image/C4D03AQGbnlB3RQ3qXA/profile-displayphoto-shrink_400_400/0/1658659120741?e=1702512000&v=beta&t=8qGVMw_xVs6gdqk0N3j8JS1IhaFqnZ1M1hKdragNPaU')",
          name: "Ivo Vilar",
          profession: "Full-Stack Pleno Grupo VOZ",
          description:
            "Jairo é um excelente profissional, dedicado, pontual, sempre está disposto a aprender mais, trabalha bem em equipe e além do profissional é uma excelente pessoa.",
						link: "https://www.linkedin.com/in/ivo-vilar/"
        },
				{
          photo:
            "url('https://media.licdn.com/dms/image/D4D03AQERDdTnvytUIw/profile-displayphoto-shrink_400_400/0/1688221330044?e=1702512000&v=beta&t=cuw2j9KkxWZVqn2N_IQvDJGCe0kM8Y0-0S0iuEZI6jw')",
          name: "Fernando Pontes",
          profession: "Desenvolvedor Flutter Senior Pulse",
          description:
            "O tempo que passei com Jairo percebi ser uma pessoa muito responsável, atencioso e zeloso com os que estão próximos. Somando a isso, está sempre procurando evoluir através dos estudos e também ajudando os outros através de tutorias e aulas particulares. Tenho ótimas lembranças do tempo que compartilhamos.",
						link: "https://www.linkedin.com/in/fernandospontes/"
        },
      ],
    };
  },
  computed: {
    currentPerson() {
      return this.people[this.currentPersonIndex];
    },
  },
  methods: {
    setNextCard(direction) {
      if (direction === "left") {
        this.currentPersonIndex =
          (this.currentPersonIndex - 1 + this.people.length) %
          this.people.length;
      } else {
        this.currentPersonIndex =
          (this.currentPersonIndex + 1) % this.people.length;
      }
    },
    toggleChicken() {
      this.isChickenVisible = !this.isChickenVisible;
      this.buttonLabel = this.isChickenVisible ? "Remove the chicken" : "Surprise me";
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Shippori+Antique&display=swap");


html {
	font-size: 12px;
}

.content-wrapper {
  width: 100vw;
	  display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

h1 {
	margin-bottom: calc(0.7rem + 0.5vmin);
	font-size: calc(2.3rem + 1vmin);
}

.blue-line {
	height: 0.3rem;
	width: 6rem;
	background-color: #2c465c;
	margin-bottom: calc(3rem + 2vmin);
}

.wrapper-for-arrows {
	position: relative;
	width: 70%;
	border-radius: 2rem;
	box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
	overflow: hidden;
	display: grid;
	place-items: center;
	margin-bottom: 3%;
}

.review-wrap {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding-top: calc(2rem + 1vmin);
	width: 100%;
}

.imgDiv {
	border-radius: 50%;
	width: calc(6rem + 4vmin);
	height: calc(6rem + 4vmin);
	position: relative;
	box-shadow: 5px -3px #2c465c;
	background-size: cover;
	margin-bottom: calc(0.7rem + 0.5vmin);
  background-image: var(--current-person-photo); 
}

.chicken {
	background-image: url("https://media0.giphy.com/media/A8Cdznswn5vnG/200w.gif?cid=790b7611e8c5980ee7141bc18ec12c49962b871eb404ba5b&rid=200w.gif&ct=s");
	width: 200px;
	height: 250px;
	position: absolute;
	top: 12%;
}

.imgDiv::after {
	content: "''";
	font-size: calc(2rem + 2vmin);
	font-family: sans-serif;
	line-height: 150%;
	color: #fff;
	display: grid;
	place-items: center;
	border-radius: 50%;
	background-color: #2c465c;
	position: absolute;
	top: 10%;
	left: -15%;
	width: calc(2rem + 2vmin);
	height: calc(2rem + 2vmin);
}

.personName {
	margin-bottom: calc(0.7rem + 0.5vmin);
	font-size: calc(1rem + 0.5vmin);
	letter-spacing: calc(0.1rem + 0.1vmin);
	font-weight: bold;
}

.profession {
	font-size: calc(0.8rem + 0.3vmin);
	margin-bottom: calc(0.7rem + 0.5vmin);
	color: #2c465c;
}

.description {
	font-size: calc(0.8rem + 0.3vmin);
	width: 70%;
	max-width: 40rem;
	text-align: center;
	margin-bottom: calc(1.4rem + 1vmin);
	color: rgb(92, 92, 92);
	line-height: 2rem;
}

.arrow-wrap {
	position: absolute;
	top: 50%;
}

.arrow {
	width: calc(1.4rem + 0.6vmin);
	height: calc(1.4rem + 0.6vmin);
	border: solid #2c465c;
	border-width: 0 calc(0.5rem + 0.2vmin) calc(0.5rem + 0.2vmin) 0;
	cursor: pointer;
	transition: transform 0.3s;
}

.arrow:hover {
	transition: 0.3s;
	transform: scale(1.15);
}

.left-arrow-wrap {
	left: 5%;
	transform: rotate(135deg);
	-webkit-transform: rotate(135deg);
}

.right-arrow-wrap {
	transform: rotate(-45deg);
	-webkit-transform: rotate(-45deg);
	right: 5%;
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
	margin-bottom: calc(1.4rem + 1vmin);
}

.surprise-me-btn:hover {
	transition: background-color 0.3s, transform 0.3s;
	background-color: rgb(255, 255, 255);
	transform: rotate(5deg);
}


@media screen and (max-width: 740px) {
	.content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
  }
	.description {
		font-size: calc(0.8rem + 0.3vmin);
		width: 70%;
		max-width: 40rem;
		text-align: center;
		margin-bottom: calc(1.4rem + 1vmin);
		color: rgb(92, 92, 92);
		line-height: 1rem;
	}
}
</style>
