<template>
  <div id="footer-container">
    <div class="footer">
      <div id="footer-logo">MS Labs</div>
    </div>
    <p id="copyright">&#169; Michael Severns</p>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
#footer-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px 0;
  font-family: Arial, sans-serif;
  color: white;
  background: none;
  position: relative;
  margin-top: auto;
}

.footer {
  width: 100%;
  max-width: 1200px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
}

#footer-logo {
  font-size: 1rem;
  font-weight: bold;
  color: #00ff00;
}

#copyright {
  text-align: center;
  margin-top: 10px;
  color: white;
}

/* Responsive Design */
@media (max-width: 768px) {
  #footer-container {
    padding: 8px 0;
  }

  .footer {
    padding: 8px;
  }

  #footer-logo {
    font-size: 0.9rem;
  }

  #copyright {
    font-size: 0.8rem;
  }
}

@media (max-width: 480px) {
  #footer-container {
    padding: 6px 0;
  }

  .footer {
    flex-direction: column;
    padding: 6px;
  }

  #footer-logo {
    font-size: 0.8rem;
    margin-bottom: 8px;
  }

  #copyright {
    font-size: 0.7rem;
  }
}
</style>