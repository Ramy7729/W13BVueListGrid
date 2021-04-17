<!-- Using registered components -->
<template>
  <div id="app">
    <page-header/>
    <page-content />
    <page-footer/>
  </div>
</template>


<script>
// Importing components to make up the content of the page.
// Each component is a module that is specific to the page.
import PageContent from './components/PageContent.vue'
import PageFooter from './components/PageFooter.vue'
import PageHeader from './components/PageHeader.vue'
// Registering components for use in other vue files.
export default {
  name: 'App',
    components: {
      PageHeader,
      PageContent,
      PageFooter
    }
}
</script>

<style>
  
  * {
    margin: 0;
    padding: 0;
  }
  
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
  }

  body {
    background-color: #ffd662ff;
  }

</style>
