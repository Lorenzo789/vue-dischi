<template>
  <main>
    <div class="container" v-if="(songs.length == 10)">
        <CardSong v-for="(song, index) in songs" :key="index" 
            :imageUrl="song.poster"
            :title="song.title"
            :author="song.author"
            :year="song.year"
            :genre="song.genre"
        />
    </div>
    <div v-else>
        <LoaderComponent />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import CardSong from "./CardSong.vue";
import LoaderComponent from "./LoaderComponent.vue";


export default {

    data: function(){
        return{
            songs: [],
        }
    },

    components: {
    CardSong,
    LoaderComponent
    },

    methods: {
        getSong(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.songs = result.data.response;
                console.log(result.data.response);
            })
        }
    },

    created(){
        setTimeout(() => this.getSong(), 500);
    }
}
</script>

<style lang="scss" scoped>
    @import'../styles/variables.scss';

    main{
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: $mainBg;
        height: calc(100vh - 70px);

        .container{
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            width: 60%;
        }
    }
</style>