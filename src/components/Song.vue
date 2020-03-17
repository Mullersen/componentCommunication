<template>
    <div id="song">
         <h2>{{ artist }}</h2>
         <p>{{ title }}</p>
         <button v-on:click="notifyParent">Add to playlist</button>
    </div>
</template>

<script>
export default {
    name: "Song",
    props: { // song has the following properties: this is what a song is made of. It expects an artist as a string, and a title as a string.
        artist: {
            type: String,
            required: true,
            default: "artist name"
        },
        title : {
            type: String, 
            required: true,
            default: "songtitle"
        }
    },
    methods: {
        notifyParent: function(){
            this.$emit("sendSong", this.artist, this.title);
        }
    }
}
</script>

<style scoped>
#song{
    padding: 4vh 2vw 4vh 2vw;
    border: black solid 1px;
}
</style>