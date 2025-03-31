<template>
  <div class="intro">
    <header class="type-effect">Michael Severns</header>
    <h1 class="type-effect type-effect-delay1">Full-Stack Java Developer</h1>
    <h2 class="type-effect type-effect-delay2"></h2>
    <img
        src="/image_67175681.JPG"
        alt="A professional photo of Michael Severns"
        class="profile-image hidden"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageSrc: "/image_67175681.JPG",
    };
  },
  mounted() {
    const profileImage = this.$el.querySelector(".profile-image");
    setTimeout(() => {
      if (profileImage) {
        profileImage.classList.remove("hidden");
        profileImage.style.visibility = "visible";
      }
    }, 2000);
  },
};
</script>

<style scoped>

.intro {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  font-family: 'Roboto', sans-serif;
  color: #00ff00;
  margin: 0;
}

.intro header {
  font-size: 3rem;
  margin-bottom: 10px;
}

.intro h1 {
  font-size: 3rem;
  margin: 0;
}

.intro h2 {
  font-size: 2rem;
  margin: 0;
}

.type-effect {
  position: relative;
  display: inline-block;
  overflow: hidden;
  white-space: nowrap;
  font-weight: bold;
  font-size: 2rem;
  text-align: center;
  margin: 0 auto;
  animation: typing 3s steps(45, end), blink-caret 0.3s step-end infinite;
  opacity: 0;
  animation-delay: 0s;
  animation-fill-mode: forwards;
  visibility: visible;
}

.type-effect-delay1 {
  animation-delay: 0.5s;
}

.type-effect-delay2 {
  animation-delay: 1s;
}

@keyframes typing {
  0% {
    width: 0;
    opacity: 1;
  }
  100% {
    width: 100%;
    opacity: 1;
  }
}

@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: #58a6ff;
  }
}


.profile-image {
  width: 200px;
  height: 200px;
  object-fit: cover;
  background-color: black; /* Black background */
  border: 5px solid #444;
  box-shadow: 0 0 10px #444;
  margin-bottom: 20px;
  opacity: 1;
  transition: opacity 0.5s ease-in-out;
  visibility: visible;
  margin-top: 20px;
}

.profile-image.hidden {
  opacity: 0;
  visibility: hidden;
}
</style>