<template>
  <div id="app">
   <Songlist @songToApp="changeSongArray" :mySongs="songs" class="block"/>  <!-- this is where i pass the property songs, which i am calling mySongs to the component called songlist -->
    <Playlist :myPlaySongs="playSongs" class="block"/>
  </div>
</template>

<script>
import Playlist from './components/Playlist.vue'
import Songlist from './components/Songlist.vue'

export default {
  name: 'App',
  components: {
    Playlist,
    Songlist
  }, 
  methods: {
    changeSongArray: function(newArtist, newTitle){
      this.playSongs.push({title: newTitle, artist: newArtist})  
        for( let i=0;  i<=this.songs.length; i++){
          if(this.songs[i].title == newTitle){
            this.songs.splice(i,1)
          }
        }
      // loop through songs, find the song with a title that matches newTitle, and remove it with splice at the correct index.
    }
  },
  data: function(){
    return{
      songs: [ // this is my data - the actual input to my components. 
        {
          title: "Yellow",
          artist: "Coldplay"
        }, 
        {
          title: "Big Smoke",
          artist: "Tash Sultana"
        },
        {
          title: "The Sweet Role",
          artist: "Betty Bass"
        },
        {
          title: "Don't kill my vibe",
          artist: "Sigrid"
        },
        {
          title: "Make it Better",
          artist: "Anderson .Paak"
        }
      ],
      playSongs: [
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 20vh 10vw 10vh 10vw;
  display: grid; 
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr;
}
.block{
  border: solid grey 1px;
}

</style>
