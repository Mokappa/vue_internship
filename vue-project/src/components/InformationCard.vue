<script setup>
defineProps(["name", "ability", "base_exp", "height", "img_sprite"])
</script>

<template>
    <div>
        <img :src="img_sprite" alt="Pokemon Image">

        <div>
            <p id="card-title">{{ name }}</p>
            
            <p id="card-description">This pokemon has {{ base_exp }} base experience, its ability is {{ ability }} and its height is {{ height }}</p>
        </div>
    </div>
</template>

<style scoped>
/* Small devices (landscape phones, less than 768px) */
@media (max-width: 767.98px) {
  
}

/* Medium devices (tablets, less than 992px) */
@media (max-width: 991.98px) {

}

/* Large devices (desktops, less than 1200px) */
@media (max-width: 1199.98px) {

}
</style>