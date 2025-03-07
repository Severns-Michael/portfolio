<template>
  <div class="project">
    <h1>Projects</h1>
    <div class="projects_list">
      <div v-for="(project, index) in projects" :key="index" class="project-item">
        <h2>{{ project.title }}</h2>
        <div class="project_imgs">
          <img
              v-for="(img, imgIndex) in project.images"
              :key="imgIndex"
              :src="img"
              :alt="'Image for ' + project.title"
              @click="openImageModal(img)"
              class="img-thumbnail"
          />
        </div>
        <p>{{ project.description }}</p>
      </div>
    </div>
    <div v-if="showModal" class="image-modal">
      <div class="modal-backdrop"
           @click="closeImageModal"></div>
      <div class="modal-content">
        <img :src="selectedImage" alt="Large View" />
        <button class="close-btn"
                @click="closeImageModal">Close</button>
      </div>
    </div>
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
            "/vue logo.png",
            "/sql.png",
          ],
        },
      ],
      showModal: false,
      selectedImage: null,
    };
  },
  methods: {
    openImageModal(img) {
      console.log("img",img);
      this.selectedImage = img;
      this.showModal = true;

    },
    closeImageModal() {
      this.showModal = false;
      this.selectedImage = null;
    },
  },
};
</script>

<style scoped>
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
  background-color: rgba(0, 0, 0, 0.8);
}
.modal-content {
  z-index: 1001;
  position: relative;
  max-width: 90%;
  max-height: 90%;

}
.modal-content img {
  width: 100%;
  height: auto;
  border-radius: 5px;
}
.modal-backdrop {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  cursor: pointer;
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
</style>