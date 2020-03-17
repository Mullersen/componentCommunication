<template>
    <div id="song">
         <h2>{{ artist }}</h2>
         <p>{{ title }}</p>
         <button>Remove</button>
    </div>
</template>

<script>
export default {
    name: "Playsong",
    props: {
        artist: {
            type: String,
            required: true,
            default: "this is an artist"
        },
        title : {
            type: String, 
            required: true,
            default: "songtitle"
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