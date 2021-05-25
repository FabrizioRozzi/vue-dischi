<template>
  <div class="d-flex justify-content-center mt-3">
    <label for="cars">Choose a genre:</label>

    <select 
      @change="changeFunction()"
      v-model="optionGenre"
      >
      <option 
        selected
        value="1">so tutti</option>
      <option
        v-for="(gen, index) in genere" :key='index'
        :value="gen">{{gen}}</option>
    </select>
  </div>
</template>

<script>

export default {
  name : 'ListGenre',
   data(){
    return{
      optionGenre:'1'
      
    }
  },
  props:{
    genere : Array
  },
  methods:{
    changeFunction(){
      this.$emit("searchOption", this.optionGenre)
    }
  }
  
}
</script>

<style lang="scss" scoped>
  label{
    color: white;
  }
</style>