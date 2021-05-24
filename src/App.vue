<template>
  <div id="app">
    <Header />
    <div class="wrap row d-flex justify-content-between">
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
  import Header from '@/components/Header.vue';

  import Album from '@/components/Album.vue';
export default {
  name: 'App',
  components: {
    Header,
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

<style lang="scss">
  @import '~bootstrap/scss/bootstrap' ;
  body{
    background-color: #1E2D3B;
  }
  .wrap{
    width: 60%;
    margin: 0 auto;
  }
</style>
