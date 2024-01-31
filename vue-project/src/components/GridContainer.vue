<script setup>
import InformationCard from './InformationCard.vue'
import { ref, computed, onBeforeMount } from 'vue'

const props = defineProps(["search_term"])
const text_data = ref()
const pokemon_count = 10

onBeforeMount(async () => {
    let pokemon_array = []

    for(let i = 1; i <= pokemon_count; ++ i) {
        const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${i}`)
        const json_data = await response.json()

        pokemon_array.push(json_data)
    }

    text_data.value = pokemon_array
})

const filteredPokemon = computed(() => {
    if(props.search_term.length === 0) {
        return text_data.value
    }

    const searchTermLowerCase = props.search_term.toLowerCase()

    return text_data.value.filter(pokemon =>
        pokemon.forms[0]?.name.toLowerCase().includes(searchTermLowerCase)
    )
})
</script>

<template>
    <InformationCard v-for="pokemon in filteredPokemon"
        :img_sprite="pokemon.sprites.front_default"
        :name="pokemon.forms[0].name" 
        :ability="pokemon.abilities[0].ability.name"
        :base_exp="pokemon.base_experience"
        :height="pokemon.height" />
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