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
            "url('https://media.licdn.com/dms/image/D4D03AQE4t2H0gJGZtg/profile-displayphoto-shrink_400_400/0/1671991801612?e=1701907200&v=beta&t=30D39saxui5BpN0wJ1Hwmle0ILP2efh6UN-tBT34ulg')",
          name: "Ygor Alberto",
          profession: "TECH LEAD DEFENSIVE SECURE",
          description:
            "Jairo é um profissional exemplar onde está sempre em busca de novos aprendizados e desafios. Seu objetivo é sempre baseado no melhor para a empresa e seu crescimento profissional e pessoal. Sabe trabalhar em equipe, comunicativo, comprometido, proativo e didático.",
            link: "https://www.linkedin.com/in/ygoralbert/",
        },
        {
          photo:
            "url('https://cdn.pixabay.com/photo/2019/02/11/20/20/woman-3990680_960_720.jpg')",
          name: "Anna Grey",
          profession: "UFC FIGHTER",
          description:
            "I'm baby migas cornhole hell of etsy tofu, pickled af cardigan pabst. Man braid deep v pour-over, blue bottle art party thundercats vape. Yr waistcoat whatever yuccie, farm-to-table next level PBR&B. Banh mi pinterest palo santo, aesthetic chambray",
        },
        {
          photo:
            "url('https://cdn.pixabay.com/photo/2016/11/21/12/42/beard-1845166_960_720.jpg')",
          name: "Branson Cook",
          profession: "ACTOR",
          description:
            "Radio telescope something incredible is waiting to be known billions upon billions Jean-François Champollion hearts of the stars tingling of the spine. Encyclopaedia galactica not a sunrise but a galaxyrise concept of the number one encyclot",
        },
        {
          photo:
            "url('https://cdn.pixabay.com/photo/2014/10/30/17/32/boy-509488_960_720.jpg')",
          name: "Julius Grohn",
          profession: "PROFESSIONAL CHILD",
          description:
            "Biscuit chocolate pastry topping lollipop pie. Sugar plum brownie halvah dessert tiramisu tiramisu gummi bears icing cookie. Gummies gummi bears pie apple pie sugar plum jujubes. Oat cake croissant bear claw tootsie roll caramels. Powder ice crea"
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

body {
	height: 100vh;
	display: grid;
	place-items: center;
}

.content-wrapper {
  width: 80%;
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
	left: -10%;
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

.move-head {
	animation: moveHead 1.55s infinite;
	animation-delay: -0.8s;
}

.hide-chicken-btn {
	border: 2px solid rgb(226, 89, 79);
	background-color: rgb(255, 224, 224);
	color: rgb(226, 79, 79);
	border-radius: 2rem;
	padding: calc(0.5rem + 0.2vmin) 0;
	width: calc(10rem + 5vmin);
	text-align: center;
	transition: background-color 0.3s, transform 0.3s;
	cursor: pointer;
	margin-bottom: calc(1.4rem + 1vmin);
}

.hide-chicken-btn:hover {
	transition: background-color 0.3s, transform 0.3s;
	background-color: rgb(255, 255, 255);
	transform: rotate(5deg);
}

@keyframes moveHead {
	0% {
	}
	25% {
		transform: translate(0.5rem, 1rem) rotate(5deg);
	}
	100% {
		transform: translate(0, 0) rotate(-5deg);
	}
}

@media screen and (max-width: 900px) {
	.content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
  }
}
</style>
