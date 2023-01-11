<script>
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';

  export default{
    components: {
      AppHeader,
      AppMain,
    }
  }
</script>

<template>
  <header>
    <AppHeader/>
  </header>

  <main>
    <AppMain/>
  </main>
</template>

<style lang="scss">

  @use './styles/partials/variables' as *;

  *,
  *::before,
  *::after{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style-type: none;
  }

  header{
    display: flex;
    align-items: center;
    height: 100px;
  }

  main{
    background-color: $main-color;
  }
</style>
