<template>
  <main>
    <div>
        <CardSong />
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
                this.songs.push(result.data.response);
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
        background-color: $mainBg;
        height: calc(100vh - 70px);

        div{
            margin: 0 auto;
            width: 60%;
        }
    }
</style>