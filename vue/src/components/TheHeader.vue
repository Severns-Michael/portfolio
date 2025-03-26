<template>
  <div id="container">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css" integrity="sha512-Evv84Mr4kqVGRNSgIGL/F/aIDqQb7xQ2vcrdIwxfjThSH8CSR7PBEakCr51Ck+w+/U6swU2Im1vVX0SVk9ABhg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <div class="navbar">
      <div id="logo">
        MS Labs
      </div>

      <!-- Desktop links -->
      <div id="links">
        <router-link :to="{ name: 'home' }" class="nav-button">Home</router-link>
        <router-link :to="{ name: 'about' }" class="nav-button">About</router-link>
        <router-link :to="{ name: 'project' }" class="nav-button">Projects</router-link>
        <a href="https://www.linkedin.com/in/michaelsevernsdev/" class="nav-button">
          LinkedIn
        </a>
        <a href="https://github.com/Severns-Michael" class="nav-button">
          Github
        </a>
      </div>

      <!-- Toggle button (visible on smaller screens) -->
      <div class="toggle_btn" @click="toggleDropdown">
        <i class="fa-solid fa-bars"></i>
      </div>

      <!-- Dropdown menu (hidden by default) -->
      <div class="dropdown_menu" v-show="dropdownVisible">
        <router-link :to="{ name: 'home' }" class="nav-button">Home</router-link>
        <router-link :to="{ name: 'about' }" class="nav-button">About</router-link>
        <router-link :to="{ name: 'project' }" class="nav-button">Projects</router-link>
        <a href="https://www.linkedin.com/in/michaelsevernsdev/" class="nav-button">
          LinkedIn
        </a>
        <a href="https://github.com/Severns-Michael" class="nav-button">
          Github
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dropdownVisible: false, // Keep track of dropdown visibility
    };
  },
  methods: {
    toggleDropdown() {
      this.dropdownVisible = !this.dropdownVisible; // Toggle visibility state
    },
    handleResize() {
      // Check if the screen is larger than 992px and reset the dropdown visibility
      if (window.innerWidth > 992) {
        this.dropdownVisible = false; // Hide dropdown if screen is enlarged
      }
    },
  },
  mounted() {
    // Add a resize event listener on mount
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    // Clean up the listener on unmount
    window.removeEventListener('resize', this.handleResize);
  },
};
</script>

<style scoped>
#container {
  width: 100%;
  display: flex;
  flex-direction: column;
  overflow: visible;
}
/* Navigation Bar */
.navbar {
  width: 100%;
  height: 60px;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
#links {
  display: flex;
  gap: 2rem;
}
.nav-button {
  text-decoration: none;
  color: inherit;
}
.toggle_btn {
  color: black;
  font-size: 2rem;
  cursor: pointer;
  display: none;
  position: absolute;
  top: 15px;
  right: 15px;
  z-index: 10;

}
@media (max-width: 992px) {
  .toggle_btn {
    display: block;
  }
}


@media (max-width: 992px) {
  #links {
    display: none;
  }
}

  .dropdown_menu {
    position: absolute;
    right: 2rem;
    top: 80px;
    width: 300px;
    background-color: #fff;
    backdrop-filter: blur(10px);
    border-radius: 7px;


  }

.dropdown_menu .nav-button {
  padding: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
}


</style>