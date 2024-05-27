<template>
  <div class="home-container">    
    <GhostCard v-for="ghost in ghosts" :key="ghost.id" :ghost="ghost"/>        
  </div>
</template>

<script>
import GhostCard from '../components/GhostCard.vue'
// @ is an alias to /src

export default {
  components: { GhostCard },
  name: 'HomeView',  
  data(){
    return{
      ghosts: [],
    }
  },
  mounted(){
    this.getAllGhost();         
  },
  methods:{
    async getAllGhost() {
      const response = await fetch('http://localhost:3000/information');
      const data = await response.json();              
      this.ghosts = data.ghosts;      
      console.log(this.ghosts);
    },
  }
}
</script>

<style scoped>
.home-container{
  display: flex;
  height: 100%;
  justify-content: center;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 12px;
}
</style>
