<!-- Collaborated with Liz. -->
<template>
  
  <div id="contentContainer">
    <!-- Using the v-on directive to listen for and trigger events -->
    <button v-on:click="viewToggle">Toggle</button>
    <!-- Binding classes with specfied data values -->
    <div v-bind:class="{gridView, listView}"  class="gridCards">
      <!-- For loop that iterates through the tweets object and binds data as needed. -->
      <div v-for="tweet in tweets" v-bind:key="tweet.tweets">
        <!-- Binded data properties accessed and used with the moustached syntax.  -->
        <!-- Data is inserted between specified tags and will be displayed on the screen. -->
        <h2>{{ tweet.username }}</h2>
        <p>{{ tweet.tweet }}</p>
        <h3>{{ tweet.created_at }}</h3>
      </div>
    </div>
  </div>

</template>

<script>
// Registering the component for use in other vue files.
export default {
  name: 'page-content',
  
  data() {
    // gridView and listView are assigned boolean values.
    // Both are being binded to specific classes using the v-on directive.
    // They will be assigned their opposite values through the use of a method.
    return {
      gridView: true,
      listView: false,
      
      tweets: [
        {
          tweet: `the Earth is definitely flat`, 
          username: `Someguy`, 
          created_at: `07-07-2009`, 
          age: 77
        },
        {
          tweet: `"How about if I sleep a little bit longer and forget all this nonsense`, 
          username: `DudefromthatKafkabook`, 
          created_at: `07-17-2011`, 
          age: 87
        },
        {
          tweet: `it's a meeeeeeeeeeeeeeeeee......Mario!!!`, 
          username: `Mario`, 
          created_at: `01-27-2012`, 
          age: 27
        },
        {
          tweet: `Beauty is everywhere. You only have to look to see it.`, 
          username: `Bob Ross`, 
          created_at: `08-27-2013`, 
          age: 37
        },
        {
          tweet: `To be without some of the things you want is an indispensable part of happiness.`, 
          username: `bert@Russ`, 
          created_at: `04-07-2015`, 
          age: 70
        },
        {
          tweet: `One must imagine Sisyphus happy.`, 
          username: `DaManCamus`, 
          created_at: `07-17-2016`, 
          age: 67
        },
        {
          tweet: `If ‘The Flintstones’ has taught us anything, it’s that pelicans can be used to mix cement.`, 
          username: `Homer_Simpson`, 
          created_at: `03-07-2017`, 
          age: 47
        },
        {
          tweet: `The man who has a conscience suffers whilst acknowledging his sin. That is his punishment-- as well as prison.`, 
          username: `Raskolnikov`, 
          created_at: `10-110-2019`, 
          age: 7
        },
        {
          tweet: `If it is not right do not do it; if it is not true do not say it.`, 
          username: `Marcus`, 
          created_at: `05-07-2020`, 
          age: 17
        },
        {
          tweet: `Don't you ever compare me to Family Guy.`, 
          username: `Cartmen`, 
          created_at: `01-07-2021`, 
          age: 57
        }
      ],
    };
  },
  
  methods: {
    // This method toggles between both classes of gridView and listView.
    // It is called upon with the click event when the user clicks on the toggle button.
    // The opposite values are assigned using the not(!) operator and enables the toggling of both views.
    viewToggle() {
      this.gridView = !this.gridView;
      this.listView = !this.listView;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#contentContainer {
  display: grid;
  place-items: center;
}

.gridView {
  max-width: 1200px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  line-height: 2em;
  gap: 2em;
  margin-top: 20px;
}

.gridView > div {
  border: 3px solid #00539CFF;
  border-radius: 20px;
  padding: 1rem;
  place-items: center;
  background-image: url("../assets/homer.jpg");
  background-size: cover;
  background-position-x: 17em;
}

.listView {
  display: grid;
  line-height: 2em;
  gap: 2em;
  margin-top: 20px;
}

.listView > div {
  border: 3px solid #00539CFF;
  border-radius: 20px;
  padding: .5rem;
  gap: 2em;
  background-image: url("../assets/cartman.png");
  background-size: cover;
  background-position: 777px;
}

button {
  margin-top: 20px;
  padding:6px 24px;
}

p {
  font-size: 1.3em;
}

</style>
