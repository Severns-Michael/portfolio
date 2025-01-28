<template>
  <div id="container">
    <!-- Header -->
    <div id="nav">
      <div id="logo">
        <img src="public/logo 3.xcf" alt="Logo" class="logo-icon" />
      </div>
      <router-link v-bind:to="{ name: 'home' }">
        <img src="public/home icon.png" alt="Home" class="nav-icon" />
      </router-link>
      <router-link v-bind:to="{ name: 'about' }">
        <img src="public/person imagine 2.jpg" alt="About" class="nav-icon" />
      </router-link>
      <router-link v-bind:to="{ name: 'project' }">
        <img src="public/project icon.png" alt="Projects" class="nav-icon" />
      </router-link>
      <a href="https://www.linkedin.com/in/michaelsevernsdev/" target="_blank">
        <img src="public/linkedin icon.png" alt="LinkedIn" class="social-icon" />
      </a>
      <a href="https://github.com/Severns-Michael" target="_blank">
        <img src="public/github icon.png" alt="GitHub" class="social-icon" />
      </a>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>

#container {
  width: 100%;
  display: flex;
  flex-direction: column;
  overflow: visible;
}

/* Navigation Bar */
#nav {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 20px;
  width: 40%;
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  margin: 0 auto;
  border-radius: 25px;
  background-color: hsla(0, 0%, 20%, 40%);
  backdrop-filter: blur(10px);
  margin-top: 10px;

}

/* Logo */
#logo {
  margin-right: 20px;
}
.logo-icon {
  width: 50px;
  height: auto;
}

/* Navigation Links */
.nav-icon,
.social-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 0 10px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.nav-icon:hover,
.social-icon:hover {
  transform: scale(1.1);
}

#content {
  margin-top: 20px;
  padding: 0 20px;
  line-height: 1.6;
  font-size: 16px;
}
</style>