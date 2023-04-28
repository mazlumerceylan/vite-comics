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
