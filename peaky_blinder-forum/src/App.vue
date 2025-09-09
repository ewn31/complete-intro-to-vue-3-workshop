<script>
import Characters from './components/Characters.vue'
export default { data(){
        return{
          showTitle: "Peaky Blinders",
          synopsis: "A crime drama about a Birmingham family gang known as the Peaky Blinders. The show takes place in England from 1919 to 1930's before the start of the second world war ",
          genre: ['crime', 'drama', 'action'],
          numberOfSeasons: 6,
          firstAired: 2014,
          stillRunning: false,

        }
      },
      components: {
        Characters
        }
}
</script>

<template>
  <div>
      <h1>{{ showTitle }}</h1>
      <p>Released: <i>{{firstAired}}</i>, Still Running: {{ stillRunning ? "Yes" : "No" }}, Number of Seasons: {{ numberOfSeasons }}</p>
      <h2>Synopsis</h2>
      <p>{{ synopsis }}</p>
      <p><b>Genre: </b> <span v-for="(topic, index) in genre" :key="`genre-${index}`"> <i>{{ topic + " " }}</i> </span> </p>
      <Characters />
    </div>
</template>

