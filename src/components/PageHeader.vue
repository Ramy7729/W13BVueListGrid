<template>
    <header>
        <h1>Tweets</h1>
    </header>
</template>

<script>
// Registering the component for use in other vue file.
export default {
  name: 'page-header'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  display: grid;
  font-size: 3em;
  color: #ffd662ff;
  background-color: #00539cff;
  height: 170px;
  place-items: center;
}
</style>
