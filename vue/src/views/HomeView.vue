<template>
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Terminal Style</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
  <div class="intro">
    <header class="type-effect">Hello! I am</header>
    <h1 class="type-effect type-effect-delay1" >Michael Severns</h1>
    <h2 class="type-effect type-effect-delay2">Full-Stack Java Developer</h2>

  </div>
  </body>
  </html>


</template>

<script>
export default {
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
  background-color: #222;
  color: #fff;

}

.intro header {
  font-size: 3rem;


}
.intro h1 {
  font-size: 3rem;

}
.intro h2 {
  font-size: 2rem;
}

.type-effect{
  animation-delay: 10s;
  position: relative;
  display: inline-block;
  overflow: hidden;
  white-space: nowrap;
  font-weight: bold;
  font-size: 2rem;
  animation: typing 3s steps(45, end), blink-caret 0.3s step-end infinite;
  text-align: center;
  margin: 0 auto;
  visibility: hidden;
  animation-fill-mode: forwards;

}
.type-effect-delay1{
  animation-delay: .5s;

}
.type-effect-delay2 {
  animation-delay: 1s;
}
@keyframes typing {
  0% {

    width: 0;
  }
  100% {
    width: 100%;
    visibility: visible;
  }
}
@keyframes blink-caret {
  from, to {
    border-color: transparent;

  }
  50% {
    border-color: #58a6ff;
  }
}


</style>
