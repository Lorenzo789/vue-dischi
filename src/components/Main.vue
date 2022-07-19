<template>
  <main>
    <div class="container">
         <CardSong v-for="(song, index) in songs" :key="index" 
            :imageUrl="song.poster"
            :title="song.title"
            :author="song.author"
            :year="song.year"
        />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import CardSong from "./CardSong.vue";


export default {

    data: function(){
        return{
            songs: [],
        }
    },

    components: { 
        CardSong 
    },

    methods: {
        getSong(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.songs = result.data.response;
                console.log(this.songs);
            })
        }
    },

    created(){
        this.getSong();
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