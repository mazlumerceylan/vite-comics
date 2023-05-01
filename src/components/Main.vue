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
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


.jumbo {
  position: relative;
  overflow: hidden;
  height: 350px;
}
  img{
   width: 100%;
  }
  .content {
  position: relative; /* Aggiunto per posizionare il bottone correttamente */
  text-align: center;
  background-color: black;
  color: white;
}

.current-series {
  position: absolute;
  top: -20px; /* Posiziona il bottone a metà tra il jumbotron e il contenitore sottostante */
  left: 25%;
  transform: translate(-50%, 0);
  font-size: 16px;
  color: white;
  background-color: #1e90ff;
  border-radius: 5px;
  padding: 12px 24px;
  cursor: pointer;
  transition: background-color 0.3s;

  &:hover {
    background-color: #007bff;
  }
}
.content {
  padding-top: 30px;
  text-align: center;
  background-color: black;
  color: white;
  
}

.comics-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  width: 70%;
  margin: 0 auto;
}

.comic-card {
  border-radius: 5px;
  padding: 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 170px;

}

.comic-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 5px;
  cursor: pointer;
}

.comic-card h3 {
  font-size: 18px;
  margin: 0.5rem 0;
  cursor: pointer;
}

.comic-card p {
  font-size: 14px;
  margin: 0;
  cursor: pointer;
}

.load-more-btn {
  font-size: 16px;
  color: white;
  background-color: #1e90ff;
  border-radius: 5px;
  padding: 12px 24px;
  margin: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;

  &:hover {
    background-color: #007bff;
  }
}

.blue-bar {
  background-color: #1e90ff;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-container {
  display: flex;
  align-items: center;
  max-width: 1200px;
  padding: 0 1rem;
}

.card {
  display: flex;
  align-items: center;
  margin-right: 4rem;
  cursor: pointer;
}

.card img {
  width: 50px;
}

.text {
  font-size: 10px;
  color: white;
  margin-left: 1rem;
}
</style>
