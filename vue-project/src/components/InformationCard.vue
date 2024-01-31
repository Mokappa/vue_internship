<script setup>
import { computed } from 'vue';

const props = defineProps(["name", "ability", "base_exp", "height", "img_sprite"])

const googleSearchLink = computed(() => {
  const searchQuery = encodeURIComponent(props.name)

  return `https://www.google.com/search?q=${searchQuery}`
})
</script>

<template>
    <a class="card-flex" :href="googleSearchLink" target="_blank">
        <img class="card-img" :src="img_sprite" alt="Pokemon Image">

        <div class="card-text-flex">
            <h2 id="card-title">{{ name }}</h2>
            
            <p id="card-description">This pokemon has {{ base_exp }} base experience, its ability is {{ ability }} and its height is {{ height }}</p>
        </div>
    </a>
</template>

<style scoped>
.card-flex {
    display: flex;
    width: fit-content;
    background: rgb(101, 47, 151);
    border-radius: 10px;
    align-items: center;
    padding: 10px;
    gap: 40px;
    text-decoration: none;
    color: inherit;
}

.card-img {
    width: 100%;
}

.card-text-flex {
    display: flex;
    flex-direction: column;
    height: fit-content;
    justify-content: space-between;
    text-align: center;
    gap: 30px;
}


/* Medium devices (tablets, less than 992px) */
@media (max-width: 991.98px) {
    .card-flex {
        display: flex;
        flex-direction: column;
        gap: 30px;
    }

    .card-img {
        width: 70%;
    }
}

/* Small devices (landscape phones, less than 768px) */
@media (max-width: 767.98px) {
    .card-flex {
        display: flex;
        flex-direction: column;
        gap: 20px;
        /* width: 40%; */
    }

    .card-img {
        width: 50%;
    }
}
</style>