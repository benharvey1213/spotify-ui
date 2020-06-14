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
  /* -webkit-font-smoothing: antialiased; */
}

/* #app { -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
} */

.menu { grid-area: menu; }
.main { grid-area: main; }
.footer { grid-area: footer; }

.grid-container {
  display: grid;
  grid-template-columns: auto minmax(0, 1fr);
  grid-template-areas:
    'menu main'
    'footer footer';
}

</style>
