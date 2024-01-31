<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <ul class="navLinks">
      <li>Link1</li>
      <li>Link2</li>
      <li>Link3</li>
    </ul>
  </header>

  <main>
  </main>

  <footer>
    <div>

    </div>
    
    <ul>
      <li>Link1</li>
      <li>Link2</li>
      <li>Link3</li>
    </ul>

    <div>

    </div>
  </footer>
</template>

<style scoped>
/* Header styling */
header {
  position: absolute;
  top: 0;
  left: 0;
  background: rgba(255, 0, 0, 0.096);
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 100px;
  align-items: center;
}

.navLinks {
  display: flex;
  gap: 50px;
  list-style: none;
}

.navLinks li {
  color: rgb(236, 236, 236);
  font-family: monospace;
  font-weight: bold;
  font-size: 2em;
  cursor: pointer;
  position: relative;
}

.navLinks li:after {
  content: '';
  position: absolute;
  bottom: -4%;
  left: 0;
  width: 100%;
  height: 2px;
  background: white;
  transition: transform .2s ease;
  transform: scaleX(0);
  transform-origin: center;
}

.navLinks li:hover:after {
  transform: scaleX(1);
}


/* Footer styling */
footer {
  display: flex;
  padding: 0 100px;
  position: absolute;
  bottom: 0%;
  width: 100%;
  background: rgba(255, 0, 0, 0.13);
}
</style>
