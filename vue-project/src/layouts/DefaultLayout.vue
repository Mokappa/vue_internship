<script setup>
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
    <img alt="Vue logo" class="logo" src="../assets/logo.svg" width="60" height="60" />

    <ul class="nav-links-header">
      <li>{{ navLinks_names[0] }}</li>
      <li>{{ navLinks_names[1] }}</li>
      <li>{{ navLinks_names[2] }}</li>
    </ul>
  </header>

  <main>
    <slot />
  </main>

  <footer>
    <img alt="Vue logo" class="flexsz-footer logo" src="../assets/logo.svg" width="60" height="60" />
    
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
main {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 100px 80px;
  color: white;
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
  main {
    padding: 100px 40px;
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
