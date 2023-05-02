<script>
import axios from "axios";
import { store } from "../data/store";
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default{
  name: "App",
  components:{
    Header,
    Main
  },
  data(){
    store
  },
  methods:{
    getApi(){
      axios.get(store.apiUrl)
      .then(result => {
        store.resultArray = result.data.data;
        console.log(this.resultArray);
      })
    }
  },
  mounted(){
    this.getApi();
  }
  

  
}

</script>

<template>

  <Header />
  <Main />

</template>

<style lang="scss" scoped>
@use './scss/main';
</style>
