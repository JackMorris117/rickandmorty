<template>
<div class="characterList">
  <ul>
      <characters-list-item v-for="(character, index) in characters" :character = "character" :key = "index"></characters-list-item>
  </ul>
  </div>
</template>

<script>
import CharactersListItem from './CharactersListItem'
export default {
    name: 'characters-list',
    props: ['characters'],
    components: {
        "characters-list-item": CharactersListItem
    }

}
</script>

<style>
h2{
    position: absolute;
    right: 1000px;
    width: 500px;
    height: 120px;
    display: flex;
    flex-direction: column;
    padding: 20px;
    align-items: center;
    width: 250px;
    height: auto;
    border-radius: 25px;
    border: 2px solid dodgerblue;
    background-color: rgba(0, 23, 85, 0.575);
}
</style>