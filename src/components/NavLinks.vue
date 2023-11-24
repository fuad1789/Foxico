<script setup>
import SearchBox from "./SearchBox.vue";
import Profile from "./Profile.vue";
import MobileMenu from "./MobileMenu.vue";
</script>

<template>
  <div class="container-navlinks">
    <Teleport to="#app">
      <div class="close-menu" v-if="isActiveMenu" @click="closeMenu" />
    </Teleport>

    <div class="links">
      <p>News</p>
      <p>Destinations</p>
      <p>Blog</p>
      <p>Contact</p>
    </div>
    <SearchBox />
    <Profile />

    <span class="mob-menu-btn" @click="toogleMenu">
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M3 12H21M3 6H21M9 18H21"
          stroke="#4D4D4D"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </span>

    <MobileMenu :isActiveMenu="isActiveMenu" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActiveMenu: false,
    };
  },

  methods: {
    toogleMenu() {
      this.isActiveMenu = !this.isActiveMenu;
    },
    closeMenu() {
      this.isActiveMenu = false;
    },
  },
};
</script>

<style scoped>
.container-navlinks {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  color: #fff;
  overflow-x: hidden;
}
.container-navlinks p {
  cursor: pointer;
  font-size: 0.9em;
  transition: all 100ms;
  padding: 10px 0;
}
.container-navlinks p:hover {
  text-shadow: 0px 0px 5px rgba(0, 0, 0, 1);
}

.links {
  display: flex;
  gap: 40px;
  align-items: center;
}

.mob-menu-btn {
  display: none;
  background: #fff;
  min-width: 35px;
  min-height: 35px;
  align-items: center;
  justify-content: center;
  border-radius: 20px;
  cursor: pointer;
  z-index: 100;
}

.close-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

@media screen and (max-width: 900px) {
  .links {
    display: none;
  }
  .mob-menu-btn {
    display: flex;
  }
}
</style>
