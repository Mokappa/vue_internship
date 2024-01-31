<script setup>
import { ref } from 'vue'
import GridContainer from './components/GridContainer.vue'

const search_term = ref("")
let navLinks_names = ["Link_1", "Link_2", "Link_3"]
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="60" height="60" />

    <ul class="nav-links-header">
      <li>{{ navLinks_names[0] }}</li>
      <li>{{ navLinks_names[1] }}</li>
      <li>{{ navLinks_names[2] }}</li>
    </ul>
  </header>

  <main>
    <h1>Pokodex</h1>
    <h4>Search for your favorite pokemon!</h4>
    
    <input v-model="search_term" type="text">

    <GridContainer :search_term="search_term" />
  </main>

  <footer>
    <img alt="Vue logo" class="flexsz-footer logo" src="./assets/logo.svg" width="60" height="60" />
    
    <ul class="flexsz-footer nav-links-footer">
      <li>{{ navLinks_names[0] }}</li>
      <li>{{ navLinks_names[1] }}</li>
      <li>{{ navLinks_names[2] }}</li>
    </ul>

    <div class="flexsz-footer">
      <p>Company Example GmbH</p>
      <p>Something Straße 48, 3348</p>
      <p>+4345213122549</p>
    </div>
  </footer>
</template>

<style scoped>
/* Header styling */
header {
  position: sticky;
  top: 0;
  left: 0;
  background: rgba(255, 0, 0, 0.096);
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 20px 80px;
  align-items: center;
}

.nav-links-header {
  display: flex;
  gap: 50px;
  list-style: none;
}

.nav-links-header li {
  color: rgb(236, 236, 236);
  font-weight: 500;
  font-size: 1.8em;
  letter-spacing: 1px;
  cursor: pointer;
  position: relative;
}

.nav-links-header li:after {
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

.nav-links-header li:hover:after {
  transform: scaleX(1);
}


/* Main styling */
main {
  min-height: 100vh;
  height: fit-content;
  display: flex;
  flex-direction: column;
  text-align: center;
  background: rgba(33, 150, 22, 0.082);
  padding: 100px 80px;
  color: white;
}


/* Footer styling */
footer {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
  padding: 20px 80px;
  width: 100%;
  background: rgba(255, 0, 0, 0.13);
}

footer p {
  color: white;
}

.flexsz-footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 18%;
  gap: 20px;
  /* background: rgba(255, 255, 255, 0.082); */
}

.nav-links-footer {
  list-style: none;
}

.nav-links-footer li {
  color: white;
  width: fit-content;
  cursor: pointer;
}

.nav-links-footer li:hover {
  text-decoration: underline;
  font-weight: 500;
}
</style>
