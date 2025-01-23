

  <template>
    <div class="terminal">
      <header class="blinking-text">Hello! I am</header>
      <h1 class="blinking-text">Michael Severns</h1>
      <h2 class="blinking-text">Full-Stack Java Developer</h2>
      <p class="blinking-text">Welcome to my terminal-style page!</p>
    </div>
  </template>

  <script>
    export default {
      name: 'TerminalPage',
    };
  </script>

  <style scoped>
    /* Add your CSS here */
    body {
      font-family: 'Courier New', Courier, monospace;
      background-color: black;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .terminal {
      background-color: black;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0, 255, 0, 0.7);
      width: 80%;
      max-width: 800px;
      text-align: left;
    }

    p {
      font-size: 18px;
      line-height: 1.5;
    }

    /* Blinking effect */
    .blinking-text {
      animation: blink 1s step-start infinite;
    }

    @keyframes blink {
      50% {
        visibility: hidden;
      }
    }
  </style>