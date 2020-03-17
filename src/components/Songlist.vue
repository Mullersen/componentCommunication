<template>
    <div>
        <Song @sendSong='forwardSong' v-for="song in mySongs" 
        v-bind:key="song.title"
        v-bind:title="song.title"
        v-bind:artist="song.artist"
        /> 
        <!-- pass the information from my array to the child component called Song by binding the values of mySongs array to a key i define.  -->
    </div>
</template>

<script>
import Song from './Song.vue'

export default {
    name: "Songlist",
    components: {
            Song,
        }, 
    props:{ // this component is expecting a property called mySongs from the parent (app) - and it is defined as an array
        mySongs: Array
    },
    methods:{
        forwardSong: function(artist, title){
            this.$emit("songToApp", artist, title);
        }
    }
}
</script>

<style scoped>

</style>