<script>
export default {
  data(){
    return {
      characters: [{name: "Thomas Shelby", dob:"01-22-1979"},{name:"Aunt Poly", dob:"01-22-1966"},{name:"Arthur Shelby", dob:"01-22-1977"}],
      favouriteList: [],
      newCharacter: {name: undefined}
    }
  },
    computed:{
        numberOfCharacters(){
          return this.characters.length
        }
      },
      methods:{
        addToFavouriteList(character){
          if (this.favouriteList.includes(character)){
            return
          }
          this.favouriteList.push(character)
        },
        addCharacter(){
          this.characters.push(this.newCharacter)
        }
      }
}
</script>

<template>
  <h2>Characters ({{ numberOfCharacters }})</h2>
      <input type="text" v-model="newCharacter.name" @keyup.enter="addCharacter()">
      <ul v-if="characters.length > 0">
        <li v-for="(character, index) in characters" :key="`character-${index}`">{{ character.name }} <button @click="addToFavouriteList(character)">Add to Favourites</button></li>
      </ul>
      <p v-else>No characters</p>
      <h2>Favourite Characters</h2>
      <p v-if="favouriteList.length === 0">No favourite Character</p>
      <ul v-else>
        <li v-for="(character, index) in favouriteList" :key="`favourite-${index}`">{{ character.name }}</li>
      </ul>
</template>
