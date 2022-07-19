<template>
    <div class="card">
        <div class="image-container">
            <img :src="imageUrl" alt="">
        </div>
        <h3>{{ title }}</h3>
        <p>{{ author }}</p>
        <p>{{ year }}</p>
    </div>
</template>

<script>
export default {
    props: {
        imageUrl: String,
        title: String,
        author: String,
        year: String,
    }
}
</script>

<style lang="scss" scoped>
    @import'../styles/variables.scss';

    .card{
        background-color: $cardBg;
        width: calc(100% / 5 - 30px);
        height: 300px;
        text-align: center;
        margin-bottom: 20px;
        margin-right: 30px;
        padding: 20px;

        h3{
            color: white;
            text-transform: uppercase;
            margin: 5px 0px;
            font-weight: bold;
        }

        p{
            color: $textColorCard;
        }
            
        img {
            object-fit: cover;
            width: 100%;
        }

    }

</style>