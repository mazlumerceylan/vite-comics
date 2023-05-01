<template>
  <main>
    <div class="jumbo">
      <img src="../assets/img/jumbotron.jpg" alt="">
    </div>
    <div class="content">
      <button class="current-series">CURRENT SERIES</button>
      <div class="comics-container">
        <div
          v-for="comic in comicsData"
          :key="comic.series"
          class="comic-card"
        >
          <img :src="comic.thumb" alt="Comic thumbnail" />
          <h3>{{ comic.series }}</h3>
          <p>{{ comic.type }}</p>
          <p>{{ comic.price }}</p>
        </div>
        <button class="load-more-btn">Load More</button>
      </div>
    </div>
    <div class="blue-bar">
      <div class="card-container">
        <div
          v-for="(card, index) in cards"
          :key="index"
          class="card"
        >
          <img :src="card.image" alt="Immagine" />
          <p class="text">{{ card.text }}</p>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    const comicsData = ref([]);

    onMounted(async () => {
      const response = await fetch('./dc-comics.json');
      comicsData.value = await response.json();
    });

    return { comicsData };
  },
  data() {
    return {
      cards: [
        {
          image: "src/assets/img/buy-comics-digital-comics.png",
          text: "DIGITAL COMICS",
        },
        {
          image: "src/assets/img/buy-comics-merchandise.png",
          text: "DC MERCHANDISE",
        },
        {
          image: "src/assets/img/buy-comics-subscriptions.png",
          text: "SUBSCRIPTION",
        },
        {
          image: "src/assets/img/buy-comics-shop-locator.png",
          text: "COMIC SHOP LOCATOR",
        },
        {
          image: "src/assets/img/buy-comics-subscriptions.png",
          text: "DC POWER VISA",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>

</style>
