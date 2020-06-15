<template>
  <div id="app">
    <div class="grid-container">
      <div class="menu">
         <LeftNav/>
      </div>
      <div class="main">
        <MainNav/>
      </div>
      <div class="footer">
        <Player/>
      </div>
    </div>   
  </div>
</template>

<script>
import LeftNav from './components/LeftNav';
import Player from './components/Player';
import MainNav from './components/MainNav';

export default {
  name: 'App',
  components: {
    LeftNav,
    Player,
    MainNav
  },
}
</script>

<style>

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
    /* background-color: black; */
    /* -webkit-font-smoothing: antialiased; */
  }

  /* html, body {
    height: 100%;
  } */

  /* #app { -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  } */

  .menu { grid-area: menu; }
  .main { grid-area: main; }
  .footer { grid-area: footer; }

  .grid-container {
    /* height: fit-content; */

    display: grid;

    grid-template-columns: auto minmax(0, 1fr);
    


    /* grid-template-rows: 1fr; */

    /* grid-template-columns: 50px 50px 1fr; */
    /* grid-template-columns: 1fr; */

    grid-template-areas:
      'menu main'
      'footer footer';


    background-color: #1D1D1D;
  }

  @media only screen and (max-width: 950px) {
    .grid-container {
      grid-template-rows: 85vh 1fr;
    }
  }

</style>
