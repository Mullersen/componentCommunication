<template>
    <div>
        <Playsong v-for="song in myPlaySongs"
            v-bind:key="song.id"
            v-bind:title="song.title"
            v-bind:artist="song.artist"/> 
    </div>
</template>

<script>
import Playsong from './Playsong.vue'

export default {
    name: "Playlist",
    components: {
        Playsong,
    }, 
    props: {
        myPlaySongs: Array
    }

}
</script>

<style scoped>

</style>