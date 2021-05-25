<template>
  <div class="container">
    <div class="max row ">
      <Album 
        v-for="(cd, index) in album"
        :key="index"
        :cd="cd"
      /> 
    </div>
  </div>
  
</template>

<script>
//importo axios
import axios from 'axios';
import Album from '@/components/Album.vue';

export default {
  name : 'Main',
  components : {
    Album
  },
  data(){
    return{
      axios,
      album:[],
    }
  },
  created(){
    //acquisisco nel created i miei dati tramite l'API
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res=>{
      
      this.album = res.data.response;
      console.log(this.album);
    })
    .catch(err=>{
      console.log(err);
    })
  },
}

</script>

<style lang="scss" scoped>
 .max{
   max-width: 1200px;
 }
</style>