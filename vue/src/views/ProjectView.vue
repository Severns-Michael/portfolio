<template>
  <div class="project">
    <h1>Projects</h1>
    <div class="projects_list">
      <div
          v-for="project in projects"
          :key="project.title"
          class="project-item"
      >
        <h2>{{ project.title }}</h2>
        <div class="project_imgs">
          <img
              v-for="img in project.images"
              :key="img"
              :src="img"
              :alt="'Image for ' + (project.title || 'Project')"
              @click.stop="openImageModal(img)"
              class="img-thumbnail"
          />
        </div>
        <p>{{ project.description }}</p>
      </div>
    </div>

    <!-- Add transition for modal -->
    <transition name="modal-fade">
      <div v-if="showModal" class="image-modal">
        <!-- Backdrop for dark background -->
        <div class="modal-backdrop" @click="closeImageModal"></div>

        <!-- Image content -->
        <div class="modal-content">
          <img :src="selectedImage" v-if="selectedImage" alt="Large View" />
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
  title: "Found Hound",
  description: "placeholder",
  images: [
  "/vue_logo.png", // Ensure the path is correct
  "/sql.png",
  ],
},
  ],
  showModal: false, // Controls whether modal is displayed
  selectedImage: null, // Dynamic image selected for modal
};
},
  methods: {
  openImageModal(img) {
  // Open modal and set selected image
  this.selectedImage = img;
  this.showModal = true;
},
  closeImageModal() {
  // Reset modal state
  this.showModal = false;
  this.selectedImage = null;
},
},
};
</script>


<style scoped>

  /* General styles */
.project {
  padding: 20px;
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

/* Modal styles */
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
  background-color: rgba(0, 0, 0, 0.8); /* Dark translucent background */
}
.modal-content {
  z-index: 1001;
  position: relative;
  max-width: 90%;
  max-height: 90%;
}
.modal-backdrop {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  cursor: pointer;
}
.modal-content img {
  width: 100%;
  height: auto;
  border-radius: 5px;
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

/* Add transition effect for modal */
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.5s ease;
}
.modal-fade-enter-from,
.modal-fade-leave-to {
  opacity: 0;
}
</style>