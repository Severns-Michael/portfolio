
<template>
  <div class="about">

    <div class="container">
      <div class="column">
      <h2>Past</h2>
      <p>I began my career in the United States Marine Corps, where I developed strong technical problem-solving and leadership skills. These experiences sparked my interest in systems optimization, leading me to transition into software development. I enrolled in Tech Elevator’s Java Development Program, where I gained full-stack development skills and further honed my problem-solving abilities, setting the foundation for my career in tech. </p>
      </div>

      <div class="column">
        <h2>Current</h2>
        <p>I am in the process of transitioning into a full-time software development career. Currently, I’m working as an intern at MusicLFG, where I apply my technical skills part-time, gaining real-world experience in the tech industry. I am also preparing for my upcoming studies in Computer Science as I begin my BS in Computer Science this May, which will further deepen my knowledge and skills.

          As I continue to build my portfolio and enhance my coding abilities, I’m actively seeking development opportunities to grow professionally. My goal is to refine my technical expertise, contribute to impactful projects, and become a stronger developer in a collaborative environment.</p>

      </div>
      <div class="column">
        <h2>Future</h2>
        <p>Looking ahead, I plan to complete my BS in Computer Science and continue my education with a Master’s in IT Project Management to transition into leadership roles within the tech industry. I’m also eager to dive into game development, with plans to create my own video game using Unity. This project will allow me to blend my technical expertise with creativity and storytelling. Ultimately, I envision myself advancing in IT Project Management, leading development teams and driving innovation while contributing to impactful projects.

        </p>
      </div>
    </div>


    <div class="skills-box">
      <h3>Skills</h3>

      <div class="checkbox-area">
        <label>
          <input type="checkbox" v-model="showBackend" /> Back-end
        </label>
        <label>
          <input type="checkbox" v-model="showFrontend" /> Front-end
        </label>
        <label>
          <input type="checkbox" v-model="showTools" /> Tools
        </label>
        <label>
          <input type="checkbox" v-model="showLearning" /> Learning
        </label>
      </div>


      <div class="skills-display">

        <div v-if="showBackend" class="skills">
          <h4>Back-end</h4>
          <div class="skills-design">
            <div class="skill-word backend">Java</div>
            <div class="skill-word backend">SQL</div>
            <div class="skill-word backend">Spring Boot</div>
          </div>
        </div>


        <div v-if="showFrontend" class="skills">
          <h4>Front-end</h4>
          <div class="skills-design">
            <div class="skill-word frontend">JavaScript</div>
            <div class="skill-word frontend">HTML</div>
            <div class="skill-word frontend">CSS</div>
            <div class="skill-word frontend">Vue.js</div>
            <div class="skill-word frontend">Bootstrap</div>
          </div>
        </div>


        <div v-if="showTools" class="skills">
          <h4>Tools</h4>
          <div class="skills-design">
            <div class="skill-word tools">Git</div>
            <div class="skill-word tools">PostgreSQL</div>
            <div class="skill-word tools">GitHub</div>
            <div class="skill-word tools">IntelliJ</div>
            <div class="skill-word tools">WebStorm</div>
            <div class="skill-word tools">Visual Studio Code</div>
            <div class="skill-word tools">Postman</div>
          </div>
        </div>


        <div v-if="showLearning" class="skills">
          <h4>Learning</h4>
          <div class="skills-design">
            <div class="skill-word learning">C#</div>
            <div class="skill-word learning">Soildity</div>
            <div class="skill-word learning">TypeScript</div>
            <div class="skill-word learning">React.js</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showBackend: true,
      showFrontend: true,
      showTools: true,
      showLearning: true,
    };
  },
};
</script>


<style scoped>
.about {
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 10px;
  overflow-y: auto;
}

.container {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 20px;
  margin-top: 20px;
  flex-wrap: wrap;
}

.column {
  flex: 1;
  padding: 20px;
  margin: 10px;
  background-color: #222;
  border: 1px solid #00ff00;
  margin-top: 20px;
  color: #ccc;
  max-height: 500px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  box-sizing: border-box;
}



/* Main Skills Box */
.skills-box {
  background-color: #222;
  border: 1px solid #00cc00;
  border-radius: 12px;
  padding: 20px;
  box-shadow: 0 4px 10px #444;
  max-width: 800px;
  margin: 0 auto;
  height: 300px;
  overflow-y: auto;
  overflow-x: hidden;
}

.skills-box h3 {
  text-align: center;
  margin-bottom: 16px;
  color:#00ff00;
}

/* Checkbox Area Styles */
.checkbox-area {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 20px;
}

label {
  font-size: 1.2em;
  font-weight: bold;
  color: #00ff00;
  display: flex;
  align-items: center;
}

input[type="checkbox"] {
  accent-color: #00cc00;
  margin-right: 8px;
}

/* Scrollable Skills Display Area */
.skills-display {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.skills h4 {
  text-align: left;
  margin-bottom: 10px;
  color: #00ff00;
}

.skills-design {
  display: flex;
  flex-wrap: nowrap;
  overflow-x: auto;
  gap: 10px;
  padding: 10px 0;
}

.skills-design::-webkit-scrollbar {
  height: 8px;
}

.skills-design::-webkit-scrollbar-thumb {
  background: #333;
  border-radius: 5px;
}

.skills-design::-webkit-scrollbar-track {
  background: #222;
}

/* Skill Word Styles */
.skill-word {
  font-size: 0.9em;
  font-weight: bold;
  color: white;
  background-color: #444;
  padding: 8px 16px;
  border-radius: 12px;
  transition: all 0.3s ease;
  white-space: nowrap;
}

.skill-word:hover {
  transform: scale(1.05);
  background-color: #00cc00;
}

/* Vertically scrollable box scrollbar styles */
.skills-box::-webkit-scrollbar {
  width: 8px;
}

.skills-box::-webkit-scrollbar-thumb {
  background: #333;
  border-radius: 5px;
}

.skills-box::-webkit-scrollbar-track {
  background: #222;
}
h2 {
  color: #00ff00;
}
/* Responsive design for smaller screens */
@media screen and (max-width: 768px) {
  .container {
    flex-direction: column;
    gap: 15px;
  }

  .column {
    flex: none;
    margin: 0;
    margin-bottom: 15px;
  }

  .skills-box {
    padding: 15px;
    height: auto;
  }

  .skills-box h3 {
    font-size: 1.2rem;
  }

  .checkbox-area label {
    font-size: 1rem;
  }

  .skill-word {
    font-size: 0.8em;
    padding: 6px 12px; /* Reduce padding for smaller text boxes */
  }
}

@media screen and (max-width: 480px) {
  .about {
    padding: 5px;
  }

  .container {
    gap: 10px;
  }

  .column {
    padding: 10px;
  }

  h2 {
    font-size: 1.2rem; /* Reduce heading size */
  }

  .skills-box {
    margin: 10px auto; /* Narrow skills-box for extra small screen */
    padding: 10px;
  }

  .skills-design {
    gap: 5px; /* Reduce gap between skills on small screens */
  }

  .skill-word {
    font-size: 0.7em; /* Smaller text for skills on narrow screens */
    padding: 4px 8px; /* Compact padding */
  }

  .checkbox-area {
    gap: 10px; /* Compact space between checkboxes */
  }

  label {
    font-size: 0.9em; /* Smaller text labels */
  }
}

</style>