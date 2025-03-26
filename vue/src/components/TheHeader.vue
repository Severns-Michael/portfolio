<template>
  <div id="container">
    <div id="nav">
      <div id="logo">
        <img src="public/logo 3(1).png" alt="Logo" class="logo-icon" />
      </div>
      <router-link v-bind:to="{ name: 'home' }" class="nav-button"> Home
      </router-link>
      <router-link v-bind:to="{ name: 'about' }" class="nav-button"> About
      </router-link>
      <router-link v-bind:to="{ name: 'project' }" class="nav-button"> Projects
      </router-link>
      <a href="https://www.linkedin.com/in/michaelsevernsdev/" target="_blank" class="nav-button"> LinkedIn</a>
      <a href="https://github.com/Severns-Michael" target="_blank" class="nav-button"> Github
<!--        <img src="public/github icon.png" alt="GitHub" class="social-icon" />-->
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
  padding: 1px 2px;
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  margin: 0 auto;
  background-color: hsla(0, 0%, 20%, 40%);
  backdrop-filter: blur(10px);
  margin-top: 10px;

}

/* Logo */
#logo {
  margin-right: 2px;
}
.logo-icon {

  width: 120px;
  height: 120px;

}
.nav-button {
  text-decoration: none;
  padding: 10px 15px;
  background-color: #007bff; /* Bootstrap primary blue */
  color: white;
  border-radius: 5px;
  margin: 5px;
  display: inline-block;
  text-align: center;
}
.nav-button:hover {
  background-color: #0056b3; /* Darker blue on hover */
  color: #ffffff;
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