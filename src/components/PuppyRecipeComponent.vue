<template>
  <div class="card">
    <div><img :src="thumbnail" /></div>
    <div class="card-information">
        <b>{{title}}</b><br /><br />
        <b>Ingredients: </b> {{ingredients}}<br /><br />
        <b>Full recipe: </b> <a :href="href" target="_blank">Click here</a><br />
    </div>
  </div>
</template>

<script>
export default {
  name: 'PuppyRecipe',
  props: ['thumbnail','title','href','ingredients']
}
</script>

<style>
#app {
  display: flex;
  flex-wrap: wrap;
}
.card {
  width: 250px;
  margin: 20px;
  border: 1px solid #555;
  border-radius: 5px;
}
.card img {
  display: block;
  margin: 20px auto 0;
  width: 90px;
}
.card-information {
  padding: 20px;
  line-height: 25px;
  font-family: sans-serif;
}
</style>
