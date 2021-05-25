<template>
  
    <div class="album text-center col-xs-12 col-sm-6 col-md-2   mt-5">
      <img 
        class="mt-2 mb-2"
        :src="cd.poster" alt=""
      >
      <h5>{{cd.title}}</h5>
      <span>{{cd.author}}</span><br>
      <span>{{cd.year}}</span>
    </div>
  
    

</template>

<script>
export default {
  name : 'Album',
  props:{
    cd : Object
  }
}
</script>

<style lang="scss" scoped>
  .album{
    background-color: #2E3A46;
    margin: 0 10px;
    height: auto;
    width: 200px;
    img{
      width: 160px;
    }
    h5{
      color: white;
    }
    span{
      color: #48434B;
    }
  }

      
        
    
  
</style>