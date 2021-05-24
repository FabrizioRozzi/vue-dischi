<template>
  <div id="app">
    <Header />
    <Main /> 

  </div>
</template>

<script>
  //importo axios
  import axios from 'axios';
  import Header from '@/components/Header.vue';
  import Main from '@/components/Main.vue';
export default {
  name: 'App',
  components: {
    Header,
    Main
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
      this.album = res.data;
      console.log(this.album);
    })
    .catch(err=>{
      console.log(err);
    })
  },
}

</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap' 
</style>
