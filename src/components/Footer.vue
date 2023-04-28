<template>
  <footer>
    <div class="footer-top">
      <div class="left-container">
        <ul v-for="(list, index) in lists" :key="index">
          <li>{{ list.title }}</li>
          <li v-for="(item, itemIndex) in list.items" :key="itemIndex">
            {{ item }}
          </li>
        </ul>
      </div>
      <div class="right-container">
        <img :src="photo" alt="Foto">
      </div>
    </div>
    <div class="footer-bottom">
      <button class="sign-in">SIGN-UP NOW!</button>
      <div class="image-group">
        <h3>{{ imageGroupTitle }}</h3>
        <div class="small-images">
          <img v-for="(image, index) in smallImages" :key="index" :src="image.src" :alt="image.alt">
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      backgroundImage: 'src/assets/img/footer-bg.jpg',
      photo: 'src/assets/img/dc-logo-bg.png',
      lists: [
        {
          title: 'DC COMICS',
          items: ['Characters', 'Comics', 'Movies', 'TV', 'Games', 'Video', 'News',]
        },
        {
          title: 'SHOP',
          items: ['Shop DC', 'Shop DC Collectibles']
        },
        {
          title: 'DC',
          items: ['Terms of use', 'Privacy Policy (New)', 'Add Choices', 'Advertisings', 'Jobs', 'Subscriptions', 'Talent Worksshop', 'CPSC Certificates', 'Ratings', 'Shop Help', 'Contact Us',]
        },
        {
          title: 'SHOP',
          items: ['DC', 'MAD Magazine', 'DC Kids', 'DC Univverse', 'DC Power Visa',]
        },
        
      ],
      imageGroupTitle: 'FOLLOW US',
      smallImages: [
        {
          src: 'src/assets/img/footer-facebook.png',
          alt: 'Facebook'
        },
        {
          src: 'src/assets/img/footer-periscope.png',
          alt: 'Periscope'
        },
        {
          src: 'src/assets/img/footer-pinterest.png',
          alt: 'Pinterest'
        },
        {
          src: 'src/assets/img/footer-twitter.png',
          alt: 'Twitter'
        },
        {
          src: 'src/assets/img/footer-youtube.png',
          alt: 'YouTube'
        }
       
      ]
    }
  }
}
</script>

<style scoped>
footer {
  font-family: Arial, sans-serif;
}

.footer-top {
  position: relative;
  background-image: url('src/assets/img/footer-bg.jpg');
  background-size: cover;
  display: flex;
  justify-content: space-between;
  padding: 20px;
  color: #fff;
}

.right-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.right-container img {
  width: 500px;
  z-index: 999;
  max-width: 100%;
  height: auto;
  
}

.left-container {
  display: flex;
  justify-content: start;
  margin-left: 180px;
  
}

ul {
  list-style: none;
  padding: 10px;
  color: white;
}

li{
  padding: 10px;
  cursor: pointer;
  font-size: 15px;

}

.footer-bottom {
  background-color: #222;
  color: #fff;
  height: 100px;
  padding: 20px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.sign-in {
  background-color: red;
  border: 2px solid white;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

.image-group {
  display: flex;
  align-items: center;
}

.small-images {
  display: flex;
  justify-content: space-between;
  margin-left: 20px;
  
}

.small-images img {
  width: 50px;
  height: 50px;
  object-fit: cover;
  margin-left: 10px;
}
</style>
