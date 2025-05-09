<template>
  <div class="project">

    <div class="projects_list">
      <div v-for="(project, index) in projects" :key="index" class="project-item">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="project_imgs">
          <img
              v-for="(img, idx) in project.images"
              :key="img"
              :src="img"
              :alt="'Image for ' + (project.title || 'Project')"
              class="img-thumbnail"
              @click.stop="openImageModal(img)"
              @error="handleImageError"
          />
        </div>
      </div>
    </div>

    <transition name="modal-fade">
      <div v-if="showModal" class="image-modal">
        <div class="modal-backdrop" @click="closeImageModal"></div>
        <div class="modal-content">
          <p v-if="!selectedImage">No image selected</p>
          <p v-else>Selected Image: {{ selectedImage }}</p>
          <img :src="selectedImage" v-if="selectedImage" alt="Large View" @error="handleImageError" />
          <button class="close-btn" @click="closeImageModal">x</button>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>

export default {
  data() {

    return {

      projects: [
        {
          title: "Tower Defense Game",
          description: "A custom-built Tower Defense game featuring a React UI and PhaserJS game engine. Players strategically place and upgrade towers across elemental paths—Fire, Ice, Lightning, and Physical—to defend against increasingly challenging waves of enemies (Grunts, Fast, Brutes, Bosses). Each tower has unique modifiers Like Freeze, Burn, Chain Lightning. Includes a visual tile-based level editor, upgrade path system (T3 max path + T2 secondary), enemy reward logic, wave progression, and endgame win/loss logic.",
          images: [
            "/public/level_editor.PNG",
              "/public/place_tower.PNG",
              "/public/gameplay.PNG",

          ]
        },
        {
          title: "Portfolio",
          description: "Developer Portfolio website, built with Vue.js, JavaScript, Html and CSS.",
        },
        {
          title: "Found Hound",
          description: "A full-stack web application that helps users find their ideal dog match by considering their preferences and swiping behavior. Built with Java, Spring Boot, Vue.js, SQL, and a RESTful API, Found Hound streamlines the adoption process by intelligently recommending dogs based on user interactions. The intuitive interface, powered by HTML, CSS, and JavaScript, provides a seamless experience for discovering, swiping, and connecting with potential furry companions.",
          images: [
            "/public/found.PNG",
            "/public/found_found_home.PNG",
            "/public/found_hound_swipe.PNG",
              "/public/landingpage.PNG",
              "/public/login.PNG",


          ],
        },
        {
          title: "Tenmo",
          description: "This backend application enables users to securely send and receive money using a RESTful API built with Java and Spring Boot. It facilitates transactions between registered users while maintaining account balances and transaction history.",
          images: [],
        },
        {
          title: "Vending Machine",
          description: "A back end application that allows users to buy items from a vending machine. Built with Java.",
          images: [],
        }
      ],
      showModal: false,
      selectedImage: null,
    };
  },
  methods: {
    openImageModal(img) {
      console.log('Image clicked:', img); // For debugging
      this.selectedImage = img;
      this.showModal = true;
    },
    closeImageModal() {
      this.showModal = false;
      this.selectedImage = null;
    },
    handleImageError(event) {
      console.error('Failed to load image:', event.target.src); // Debug
      event.target.src = '/default-placeholder.png'; // Fallback image path
    },
  },
};
</script>


<style scoped>
h2 {
  color: #00ff00;
}
p {
  color: #ccc;
}

html, body {
  height: auto;
  min-height: 100vh;
}

.project {
  padding: 20px;
  min-height: 100vh;
}
.projects_list {
  display: flex;
  flex-direction: column;
  gap: 20px;
  max-height: 800px;
  overflow-y: auto;
  padding-right: 10px;
  background-color: #222222;
  scrollbar-width: thin;
  scrollbar-color: #ccc transparent;
}
.projects_list::-webkit-scrollbar {
  width: 8px;
}
.projects_list::-webkit-scrollbar-thumb {
  background-color: #ccc;
  border-radius: 10px;
}
.projects_list::-webkit-scrollbar-track {
  background: transparent;
}
.project-item {
  padding: 20px;
  border-radius: 5px;
}
.project_imgs {
  display: flex;
  gap: 10px;
  margin: 10px 0;
}
.project_imgs img {
  cursor: pointer;
  width: 100px;
  height: 80px;
  border: 1px solid #ddd;
  border-radius: 5px;
  transition: transform 0.2s ease;
}
.project_imgs img:hover {
  transform: scale(1.1);
}

.image-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}
.modal-content {
  z-index: 1001;
  position: relative;
  max-width: 90%;
  max-height: 90%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4)
}
.modal-content img {
  width: auto;
  height: auto;
  max-width: 100%;
  max-height: 100%;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7); /* translucent black */
  z-index: 1000;
}
.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background: red;
  color: white;
  border: none;
  border-radius: 50%;
  width: 30px;
  height: 30px;
  font-size: 16px;
  cursor: pointer;
}
.close-btn:focus {
  outline: 2px solid white;
  outline-offset: 2px;
}
</style>