<template>
  <div  class="characterDetail">
      <p>Name: {{character.name}}</p>
      <img :src="character.image" class="portrait">
      <p>Species: {{character.species}}</p>
      <p>Current Status: {{character.status}}</p>
      <p>Current Location: {{character.location.name}}</p>
      <p>Episode Appearances: {{character.episode.length}}  </p>

  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
    name: 'characters-list-item',
    props: ['character'],
    methods: {
        handleClick(){
            eventBus.$emit('character-selected', this.beer);
        }
    }

}
</script>

<style>

.characterDetail{
    position: absolute;
    right: 500px;
    width: 200px;
    height: 120px;
    display: flex;
    flex-direction: column;
    padding: 20px;
    align-items: right;
    width: 300px;
    height: auto;
    border-radius: 25px;
    border: 2px solid dodgerblue;
    background-color: rgba(0, 23, 85, 0.575);
}

</style>