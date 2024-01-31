<script setup>
import DefaultLayout from './layouts/DefaultLayout.vue'
import GridContainer from './components/GridContainer.vue'
import { ref } from 'vue'

const search_term = ref("")
</script>

<template>
  <DefaultLayout>
    <div id="ball-bg"></div>

    <section class="hero-content">
      <h1>Pokodex</h1>
      <h4>Search for your favorite pokemon!</h4>
    
      <input v-model="search_term" type="text" placeholder="Type in your favorite pokemon">
    </section>

    <GridContainer :search_term="search_term" />
  </DefaultLayout>
</template>

<style scoped>
/* Main styling */
#ball-bg {
  position: absolute;
  right: 14%;
  top: 15%;
  width: 300px;
  height: 300px;
  background: radial-gradient(circle at 65% 15%, white 1px, rgb(224, 37, 31) 3%, rgb(66, 55, 55) 60%, rgb(143, 136, 136) 70%);
  border-radius: 50%;
  filter: blur(2px);
}

.hero-content {
  width: 60%;
  background: rgba(81, 0, 128, 0.24);
  backdrop-filter: blur(20px);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
  padding: 40px 40px 100px 40px;
  margin-bottom: 100px;
  box-shadow: 0px 0px 40px rgba(24, 1, 78, 0.14);
}

.hero-content h1 {
  font-size: 6em;
}

.hero-content h4 {
  font-size: 2em;
  font-weight: 400;
}

.hero-content input {
  text-align: center;
  margin-top: 80px;
  width: 60%;
  height: 6vh;
  padding: 12px;
  font-size: 1.3em;
  background: transparent;
  border: none;
  border-bottom: 2px solid rgb(197, 89, 0);
  color: white;
}

.hero-content input::placeholder {
  color: rgb(202, 91, 0);
}

.hero-content input:focus {
  outline-width: 0;
}


@media (max-width: 991.98px) {
  /* Main styling */
  #ball-bg {
    right: 15%;
    top: 20%;
    width: 240px;
    height: 240px;
  }
  
  .hero-content {
    width: 100%;
  }
}

/* Small devices (landscape phones, less than 768px) */
@media (max-width: 767.98px) {
  /* Main styling */
  #ball-bg {
    right: 20%;
    top: 25%;
    width: 140px;
    height: 140px;
  }

  .hero-content {
    width: 100%;
    padding: 40px;
  }

  .hero-content h1 {
    font-size: 4em;
  }

  .hero-content h4 {
    font-size: 1.6em;
  }

  .hero-content input {
    width: 100%;
  }
}
</style>
