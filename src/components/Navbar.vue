<template>
  <div class="header-line">

  </div>
  <nav>
    <div class="logo">
      <img src="../assets/img/dc-logo.png" alt="">
    </div>
    <ul class="menu">
      <li
        v-for="(section, index) in sections"
        :key="index"
        @mouseenter="activateItem(index)"
        @mouseleave="deactivateItem(index)"
        :class="{ active: activeItem === index }"
      >
        {{ section.title }}
        <div class="hover-line"></div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      activeItem: null,
      sections: [
        { title: "CHARACTERS" },
        { title: "COMICS" },
        { title: "MOVIES" },
        { title: "TV" },
        { title: "GAMES" },
        { title: "COLLECTIBLES" },
        { title: "VIDEOS" },
        { title: "FANS" },
        { title: "NEWS" },
        { title: "SHOP" },
      ],
    };
  },
  methods: {
    activateItem(index) {
      this.activeItem = index;
    },
    deactivateItem(index) {
      this.activeItem = null;
    },
  },
};
</script>

<style lang="scss" scoped>
.header-line{
  width: 100%;
  height: 50px;
  background-color: black;
}

nav {
  width: 70%;
  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background-color: white;
}

img{
  width: 50px;
}

.menu {
  display: flex;
  list-style: none;
  gap: 1rem;
  margin: 0;
  padding: 20px;
}

.menu li {
  cursor: pointer;
  color: black;
  position: relative;
  &.active {
    color: blue;
  }
}

.menu li:hover .hover-line {
  width: 100%;
}

.hover-line {
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 0;
  height: 3px;
  background-color: red;
  transition: width 0.3s ease;
}
</style>
