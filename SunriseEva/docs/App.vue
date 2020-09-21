<template>
  <div id="app">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>

html, body {
/*    max-width: 100vw;
    min-height: calc(100vh - 550px);
    background-color: #03112c;
    color: white;
    text-transform: uppercase;
    text-align: center;
    font-family: helvetica, arial;
    overflow: hidden;*/
  margin: 0;
  height: 100vh;
  max-width: 100vw;
  overflow: hidden;
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
}


/* Mobile first queries */

#app {

  }

/* Larger than mobile */
@media (min-width: 400px) {

}

/* Larger than phablet */
@media (min-width: 550px) {

}

/* Larger than tablet */
@media (min-width: 750px) {

}

/* Larger than desktop */
@media (max-width: 1024px) {
html {
    background-color: black;
  }

}


/* Larger than desktop */
@media (min-width: 1024px) {
#app {
    width: 100%;
    height: 100%;
  }
}

/* Larger than Desktop HD */
@media (min-width: 1200px) {

}


</style>
