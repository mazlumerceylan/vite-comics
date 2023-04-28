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
