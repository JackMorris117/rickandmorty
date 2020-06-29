<template>
<ul>
  <li v-on:click="handleClick">{{character.name}}</li>
  </ul>
</template>

<script>
import {eventBus} from '../main.js'
export default {
    name: 'characters-list-item',
    props: ['character'],
    methods: {
        handleClick(){
            eventBus.$emit('character-selected', this.character)
        }
    }

}
</script>

<style>
li {
    position: relative;
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