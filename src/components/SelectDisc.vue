<template>
    <div>
        <select name="genre" id="genre" v-model="selected"
            @keyup.enter="$emit('search', selected)">
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
            <option value="rock">Rock</option>
        </select>

        {{ selected }}
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

    select{
        padding: 10px;
        text-transform: uppercase;
        font-weight: bold;

        option{
            text-transform: uppercase;
            font-weight: bold;
        }
    }

</style>