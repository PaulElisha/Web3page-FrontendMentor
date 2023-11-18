<script setup>
import HomeContainer from '../components/HomeContainer.vue'
import Features from '../data/Features.json'
import retro from '../assets/image-retro-pcs.jpg'
import laptop from '../assets/image-top-laptops.jpg'
import gaming from '../assets/image-gaming-growth.jpg'
import { ref } from 'vue'

const CardData = [
  {
    id: '01',
    img: retro,
    title: 'Reviving Retro PCs',
    text: 'What happens when old PCs are given modern upgrades?'
  },
  {
    id: '02',
    img: laptop,
    title: 'Top 10 Laptops of 2022',
    text: 'Our best picks for various needs and budgets.'
  },
  {
    id: '03',
    img: gaming,
    title: 'The Growth of Gaming',
    text: 'How the pandemic has sparked fresh opportunities.'
  }
]

const features = ref(Features)
const cardData = ref(CardData)
</script>

<template>
  <HomeContainer>
    <main>
      <section class="grid-container">
        <div class="one">
          <picture>
            <!-- For smaller screens (mobile) -->
            <source media="(max-width: 600px)" srcset="../assets/image-web-3-mobile.jpg" />

            <!-- For larger screens (desktop) -->
            <source media="(min-width: 768px)" srcset="../assets/image-web-3-desktop.jpg" />

            <!-- Default image in case the browser doesn't support <picture> -->
            <img src="../assets/image-web-3-mobile.jpg" alt="" />
          </picture>
        </div>

        <div class="three">
          <h1>The Bright Future Of Web3.0?</h1>
        </div>

        <div class="four">
          <h3>
            We dive into the next evolution of the web that claims to put the power of the platforms
            back into the hands of the people. But is it really fulfilling its promise?
          </h3>

          <button>READ MORE</button>
        </div>

        <div class="two">
          <h1>New</h1>
          <div class="feature" v-for="feature in features" :key="feature.id">
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.text }}</p>
            <hr :style="{ marginTop: '40px' }" />
          </div>
        </div>

        <div class="five" v-for="data in cardData" :key="data.id">
          <div class="img">
            <img :src="data.img" alt="" />
          </div>
          <div class="item">
            <div class="id">{{ data.id }}</div>
            <div class="title">{{ data.title }}</div>
            <div class="text">{{ data.text }}</div>
          </div>
        </div>
      </section>
      <p :style="{ textAlign: 'center' }">Challenge by Frontend Mentor. Coded by Paul.</p>
    </main>
  </HomeContainer>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: 400px 400px 400px;
  gap: 20px 15px;
}

/* .grid-container > div {
  border: 1px solid black;
} */

.one {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row: 1;
}

.one img {
  width: 100%;
}

.two {
  grid-row-start: 1;
  grid-row-end: 3;
  grid-column: 3;
  width: 370px;
}

.two {
  padding: 15px 30px;
  background-color: hsl(240, 100%, 5%);
}

.two h1 {
  color: hsl(35, 77%, 62%);
  font-size: 40px;
  font-weight: 700;
}

.feature h3 {
  color: white;
  font-size: 22px;
  font-weight: 700;
  cursor: pointer;
  transition: 1s linear;
}

.feature h3:hover {
  color: hsl(35, 77%, 62%);
}

.feature p {
  color: hsl(233, 8%, 79%);
}

.three h1 {
  font-size: 50px;
  font-weight: 800;
  color: hsl(240, 100%, 5%);
}

.four {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

.four h3 {
  font-size: 17px;
  color: hsl(236, 13%, 42%);
}

.four button {
  outline: none;
  border: none;
  background-color: hsl(5, 85%, 63%);
  width: 180px;
  padding: 16px;
  color: white;
  font-size: 15px;
  font-weight: 700;
  cursor: pointer;
  transition: 1s linear;
}

.four button:hover {
  background-color: hsl(240, 100%, 5%);
}
.five {
  display: grid;
  grid-template-columns: 150px 240px;
  gap: 10px;
}

.item {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  margin: 20px 0;
}

.img > img {
  grid-column: 1;
  grid-row-start: 1;
  grid-row-end: 4;
  width: 100%;
}

.id {
  grid-column: 2;
  grid-row: 1;
  color: hsl(233, 8%, 79%);
  font-size: 35px;
  font-weight: 700;
}

.title {
  font-size: 20px;
  color: hsl(240, 100%, 5%);
  font-weight: 800;
  cursor: pointer;
  transition: 1s linear;
}

.title:hover {
  color: hsl(5, 85%, 63%);
}

.text {
  color: hsl(233, 8%, 79%);
  font-size: 16px;
  font-weight: 700;
}

@media screen and (max-width: 600px) {
  .grid-container {
    display: flex;
    flex-direction: column;
    justify-content: center;

    /* grid-template-columns: 400px 400px 400px; */
    /* gap: 20px 15px; */
  }
  .two {
    grid-row: 2;
    width: 100%;
  }

  .three h1 {
    font-size: 45px;
    display: flex;
    justify-content: flex;
    align-items: center;
    width: 100%;
  }

  .four {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }
  .four h3 {
    font-size: 20px;
    color: hsl(236, 13%, 42%);
  }

  .item {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }

  .id {
    font-size: 25px;
  }

  .title {
    font-size: 16px;
  }
  .text {
    font-size: 14px;
  }
}
</style>
