<template>
  <header>
    <i class="bi bi-spotify"></i>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    @import'../styles/variables.scss';
    @import'../../node_modules/bootstrap-icons/font/bootstrap-icons.css';

    header{
        height: 70px;
        padding: 10px 20px;
        background-color: $headerBg;

        i{
            color: #1dd45d;
            font-size: 40px;
        }
    }
</style>