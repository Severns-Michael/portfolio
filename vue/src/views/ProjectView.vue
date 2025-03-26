<template>
  <div class="project">
    <h1>Projects</h1>
    <div class="projects_list">
      <div v-for="(project, index) in projects" :key="index" class="project-item">
        <h2>{{ project.title }}</h2>
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
        <p>{{ project.description }}</p>
      </div>
    </div>

    <transition name="modal-fade">
      <div v-if="showModal" class="image-modal">
        <div class="modal-backdrop" @click="closeImageModal"></div>
        <div class="modal-content">
          <p v-if="!selectedImage">No image selected</p> <!-- For debugging -->
          <p v-else>Selected Image: {{ selectedImage }}</p> <!-- Debugging -->
          <img :src="selectedImage" v-if="selectedImage" alt="Large View" @error="handleImageError" />
          <button class="close-btn" @click="closeImageModal">Close</button>
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
          title: "MusicLFG",
          description: "placeholder",
          images: ["/vue_logo.png", "/sql.png"],
        },
        {
          title: "Portfolio",
          description: "placeholder",
        },
        {
          title: "Found Hound",
          description: "placeholder",
          images: ["/vue_logo.png", "/sql.png"],
        },
        {
          title: "Tenmo",
          description: "placeholder",
          images: ["/vue_logo.png", "/sql.png"],
        },
        {
          title: "Vending Machine",
          description: "placeholder",
          images: ["/vue_logo.png", "/sql.png"],
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
}
.project-item {
  border: 1px solid #ccc;
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
  height: auto;
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