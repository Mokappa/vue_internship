<script setup>
import { ref } from 'vue'
import GridContainer from './components/GridContainer.vue'

const search_term = ref("")
let navLinks_names = ["Link_1", "Link_2", "Link_3"]


window.addEventListener("scroll", function() {
    if(window.scrollY > 0) {
        document.querySelector(".nav").classList.add("scrolled")
      }
      else {
        document.querySelector(".nav").classList.remove("scrolled")
    }
})
</script>

<template>
  <header class="nav">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="60" height="60" />

    <ul class="nav-links-header">
      <li>{{ navLinks_names[0] }}</li>
      <li>{{ navLinks_names[1] }}</li>
      <li>{{ navLinks_names[2] }}</li>
    </ul>
  </header>

  <main>
    <div id="ball-bg"></div>

    <section class="hero-content">
      <h1>Pokodex</h1>
      <h4>Search for your favorite pokemon!</h4>
    
      <input v-model="search_term" type="text" placeholder="Type in your favorite pokemon">
    </section>

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
      <p><b>Company Example GmbH</b></p>
      <p>Something Straße 48, 3348</p>
      <p>+4345213122549</p>
    </div>
  </footer>
</template>

<style scoped>
/* Header styling */
.nav {
  position: sticky;
  z-index: 2;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 20px 80px;
  align-items: center;
  transition: .2s ease;
}

.scrolled {
  background: rgb(25, 0, 58);
}

.nav-links-header {
  display: flex;
  gap: 100px;
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

main {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 100px 80px;
  color: white;
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


/* Footer styling */
footer {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
  padding: 60px 80px;
  width: 100%;
  background: rgb(25, 0, 58);
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
  /* Header styling */
  .nav {
    padding: 20px 40px;
  }
  .nav-links-header {
    gap: 40px;
    font-size: .8em;
  }


  /* Main styling */
  #ball-bg {
    right: 20%;
    top: 25%;
    width: 140px;
    height: 140px;
  }

  main {
    padding: 100px 40px;
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


  /* Footer styling */
  footer {
    flex-direction: column;
    gap: 80px;
    padding: 60px 40px;
    width: 100%;
  }

  .flexsz-footer {
    width: 100%;
    gap: 20px;
  }

  .nav-links-footer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 40px;
  }
}
</style>
