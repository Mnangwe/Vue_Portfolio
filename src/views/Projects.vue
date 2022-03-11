<template>
  <section class="projects view" :class="{viewopen: opened}">
      <div class="container">
          <div class="row text-start section-title" style="">
              <h2 class="">My Portfolio</h2>
            
          </div>
          <hr>
          <div class="row">
            <div class="offset">
              
            </div>
              <Work />
               	
          </div>
            
      </div>
    
  </section>
    
  
</template>

<script>
import Work from '../components/Work.vue'
export default {
    name: "Projects",
    components: {
        Work
    }
    
}
</script>

<style scoped>

  .heading {
  width: 150px;
  height: 2px;
  background: #42b983;
  border-radius: 5px;
  margin-left: 30px;
  margin-bottom: 30px;
}
@media screen and (max-width: 1600px) {
    .image-card {
        height: 200px;
    }
}
</style>