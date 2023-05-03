<script>
import axios from "axios";
import { store } from "../data/store";
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import '/node_modules/bootstrap/scss/bootstrap.scss';


export default{
  name: "App",
  components:{
    Header,
    Main
  },
  data(){
    return {
          store
        }
  },
  methods:{
    getApi(){
      axios.get(store.apiUrl)
      .then(result => {
        store.resultArray = result.data.data;
        store.resultArray = store.resultArray.slice(0,15);
        console.log(store.resultArray);
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
