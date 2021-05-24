<template>
  
   
      <div class=" col-sm-6 col-md-4 col-lg-3 mb-5">

          <img :src="cd.poster" alt="">
          <h3>{{cd.title}}</h3>
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
  
      
        img{
          height: 150px;
        }
    
  
</style>