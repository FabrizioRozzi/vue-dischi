<template>
  <div class="d-flex justify-content-center mt-3">
    <label for="cars">Choose a genre:</label>

    <select name="cd" id="cd">
      <option
      v-for="(cd, index) in album" :key='index'
       value="volvo">{{cd.genre}}</option>
    </select>
  </div>
</template>

<script>
export default {
  name : 'ListGenre',
  props:{
    cd : Object
  }
}
</script>

<style lang="scss" scoped>
  label{
    color: white;
  }
</style>