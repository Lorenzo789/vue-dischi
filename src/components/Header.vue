<template>
  <header>
    <i class="bi bi-spotify"></i>
    <SelectDisc />
  </header>
</template>

<script>
import SelectDisc from './SelectDisc.vue';
export default {
  components: { SelectDisc }
}
</script>

<style lang="scss" scoped>
    @import'../styles/variables.scss';
    @import'../../node_modules/bootstrap-icons/font/bootstrap-icons.css';

    header{
        height: 70px;
        padding: 10px 20px;
        background-color: $headerBg;
        display: flex;
        justify-content: space-between;

        i{
          color: #1dd45d;
          font-size: 40px;
        }
    }
</style>