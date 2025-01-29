
<template>
  <div class="about">
    <h1>About My</h1>

    <div class="container">
      <div class="column">
      <h2>Past</h2>
      <p>this would be my past description</p>
      </div>

      <div class="column">
        <h2>Current</h2>
        <p>this would be my current description</p>

      </div>
      <div class="column">
        <h2>Future</h2>
        <p>this would be my future description</p>
      </div>
    </div>

      <div class="skills">
        <h2>Backend</h2>
      </div>
      <div class="skills-design">
        <div class="skill-logo">
          <img src="public/java logo.png" alt="Java"/>
          <img src="public/sql.png" alt="sql"/>
          <img src="public/springboot logo.png" alt="springboot"/>

        </div>
        <div class="skills">
          <h2>Frontend</h2>
        </div>
        <div class="skills-design">
          <div class="skill-logo">
            <img src="public/JS logo.png" alt="JS"/>
            <img src="public/html logo.png" alt="html"/>
            <img src="public/css logo.png" alt="css"/>
            <img src="public/vue logo.png" alt="Vue"/>

          </div>
        </div>


        <div class="skills">
          <h2>tools</h2>
        </div>
        <div class="skills-design">
          <div class="skill-logo">
            <img src="public/git logo.png" alt="git"/>
            <img src="public/postgres.png" alt="postgres"/>


          </div>
        </div>
      </div>


  </div>
</template>

<script>
export default {

};

</script>


<style scoped>
.about {
  background-size: cover;
  background-position: center;
  height: 100vh;
}
.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 20px;


}
.column {
  flex: 2;
  padding: 20px;
  margin: 10px;
  background-color: #fff;
  border: 1px solid #ccc;
  margin-top: 100px;

}
.skills-design {
  width: 100%;
}

.skill-logo {
  display: flex;
  justify-content: center;

 gap: 20px;
  margin: 20px auto;

}

.skill-logo img {
width: 100px;
  height: 100px;
  justify-content: space-evenly;

}


</style>