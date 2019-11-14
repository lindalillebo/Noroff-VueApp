<template>
  <div id="app">
      <PuppyRecipe v-bind:key="recipe.id" v-for="recipe in recipes"
                  v-bind:thumbnail="recipe.thumbnail"
                  v-bind:title="recipe.title"
                  v-bind:ingredients="recipe.ingredients"
                  v-bind:href="recipe.href">
      </PuppyRecipe>
  </div>
</template>

<script>
import PuppyRecipe from './components/PuppyRecipeComponent.vue'

export default {
  name: 'app',
  components: {
    PuppyRecipe
  },
  data(){
    return{
      recipes: []
    }
  },
  beforeMount: function(){
    const app = this;
    const conversionUrl = 'https://quiet-wind-54e3.my-cors-proxy.workers.dev/?';
    const url = 'http://www.recipepuppy.com/api/';

      fetch(conversionUrl + url)
      .then(function(response) {
          return response.json();
      })
      .then(function(result){
          app.recipes = result.results;
      })
  }
}

</script>
