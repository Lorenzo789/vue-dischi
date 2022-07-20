<template>
    <div>
        <label for="genre">Select a genre</label>
        <select name="genre" id="genre" v-model="selected"
            @change="$emit('search', selected)">
            <option value="all">All</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
            <option value="rock">Rock</option>
        </select>
    </div>
</template>

<script>
export default {
    data: function(){
        return{
            selected: '',
        }
    }
}
</script>

<style lang="scss" scoped>
    @import'../styles/variables.scss';
    div{
        align-self: baseline;
        position: relative;
        top: 10px;
        left: 610px;

        label{
            text-transform: uppercase;
            color: white;
            font-weight: bold;
            padding-right: 10px
        }

        select{
            padding: 10px;
            text-transform: uppercase;
            font-weight: bold;

            option{
                text-transform: uppercase;
                font-weight: bold;
            }
        }
    }

</style>