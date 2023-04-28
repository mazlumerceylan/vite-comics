<template>
  <main>
    <div class="content">
      Content goes here
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
export default {
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
.content {
  background-color: black;
  color: white;
  font-size: 50px;
  height: 200px;
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

.card img{
  width: 50px;
}

.text {
  font-size: 10px;
  color: white;
  margin-left: 1rem;
}
</style>
