<template>
  <div id="app">
    
    <character-detail :character="selectedCharacter"></character-detail>
    <characters-list :characters="characters"></characters-list>


  </div>
</template>

<script>
import {eventBus} from './main.js'
import CharactersList from './components/CharactersList.vue'
import CharacterDetail from './components/CharacterDetail'

export default {
  data(){
    return{
      characters: [],
      selectedCharacter: null
    }

  },
  name: 'App',
  components: {
    "characters-list": CharactersList,
    "character-detail": CharacterDetail
    
  },

 mounted() {
    fetch('https://rickandmortyapi.com/api/character')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
    
 }
}
</script>

<style>
#app {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #eff7ff;
  background-image: url("./assets/wallpaper.jpg");
  
}

</style>
