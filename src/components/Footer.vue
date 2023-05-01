<template>
  <footer>
    <div class="footer-top">
      <div class="left-container">
        <ul v-for="(list, index) in lists" :key="index">
          <li class="title">{{ list.title }}</li>
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

<style lang="scss" scoped>

</style>
