<template>
  <div class="projects view" :class="{viewopen: opened}">
      <div class="container">
          <div class="row" style="flex-direction: column">
              <h3 class="display-6">My Portfolio</h3>
            <div class="heading"></div>
          </div>
          <hr>
          <div class="row">
              <Work />
          </div>
            
      </div>
    
    </div>
    
  
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
.container {
  text-align: start;
  margin: auto;
  padding: 60px 0 70px;
}
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