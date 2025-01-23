<template>
  <div id="container">
    <!-- Navigation Bar -->
    <div id="nav">
      <!-- Logo on the left side -->
      <div id="logo">
        <img src="../assets/logo.png" alt="Logo" class="logo-icon" />
      </div>

      <!-- Navigation Images (Home, About, Projects, etc.) -->
      <router-link v-bind:to="{ name: 'home' }">
        <img src="fallout home button.PNG" alt="Home" class="nav-icon" />
      </router-link>
      <router-link v-bind:to="{ name: 'about' }">
        <img src="../assets/about.png" alt="About" class="nav-icon" />
      </router-link>
      <router-link v-bind:to="{ name: 'project' }">
        <img src="../assets/projects.png" alt="Projects" class="nav-icon" />
      </router-link>

      <!-- Social Media Icons -->
      <a href="https://www.linkedin.com/in/michaelsevernsdev/" target="_blank">
        <img src="../assets/linkedin.png" alt="LinkedIn" class="social-icon" />
      </a>
      <a href="https://github.com/Severns-Michael" target="_blank">
        <img src="../assets/github.png" alt="GitHub" class="social-icon" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  // Add component logic if needed
}
</script>

<style scoped>
/* Container to hold the navbar and social media icons */
#container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

/* Navigation Bar Styling (combined with Social Media Icons) */
#nav {
  display: flex;
  justify-content: flex-start; /* Align items from left to right */
  align-items: center;
  background-color: #333;
  padding: 10px 0;
  width: 100%;
}

/* Logo Styling */
#logo {
  margin-right: 20px; /* Space between logo and nav items */
}

.logo-icon {
  width: 50px; /* Set size of the logo */
  height: auto;
}

/* Navigation Images Styling (Home, About, Projects, etc.) */
#nav a {
  display: inline-block;
  margin: 0 10px;
}

.nav-icon {
  width: 40px; /* Set size of the navigation icons */
  height: 40px;
  border-radius: 50%; /* Optional: Make icons circular */
  object-fit: cover;
  transition: transform 0.3s ease;
}

.nav-icon:hover {
  transform: scale(1.1); /* Zoom effect on hover */
}

/* Social Media Icons Styling */
.social-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  object-fit: cover;
  transition: transform 0.3s ease;
  margin-left: 10px; /* Add space between the links and icons */
}

.social-icon:hover {
  transform: scale(1.1); /* Zoom effect on hover */
}
</style>