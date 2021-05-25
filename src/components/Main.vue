<template>
  <div class="container">
    <div class="max d-flex justify-content-center row ">
      <ListGenre 
        :genere="genere"
        @searchOption="searching"
      />
      <Album 
        v-for="(cd, index) in filteredAlbum"
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
import ListGenre from '@/components/ListGenre.vue';

export default {
  name : 'Main',
  components : {
    Album,
    ListGenre
  },
  data(){
    return{
      axios,
      album:[],
      genere:[],
      genSel:'1',

    }
  },
  computed:{
    filteredAlbum(){
      if(this.genSel === '1'){
        return this.album
       
      }
      // console.log(this.album);
      return this.album.filter(item => item.genre.includes(this.genSel))
    }
  },
  methods:{
    dioPorco(){
      this.album.forEach(el =>{
        if(!this.genere.includes(el.genre)){
          this.genere.push(el.genre)
          console.log(this.genere);
        }
             
      })
    },
    searching(gen){
      this.genSel = gen;
    }
  },
  created(){
    //acquisisco nel created i miei dati tramite l'API
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res=>{
      
      this.album = res.data.response;
      this.dioPorco()
    })
    .catch(err=>{
      console.log(err);
    })
    
  },
  mounted(){
    
  },
  

}

</script>

<style lang="scss" scoped>
  .container{
    width: 60%;
  }
 .max{
   max-width: 1200px;
 }
</style>