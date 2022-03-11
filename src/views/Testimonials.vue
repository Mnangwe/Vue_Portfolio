<template>
  <section class="testimonial view" :class="{viewopen: opened}">
    <div class="container">
      <div class="row text-start section-title" style="">
        <h2 class="">Testimonials</h2>
        
      </div>
    <hr>
    <div class="row">
      <p class="muted">Look at what my lovely colleagues, lecturers and friends have to say about me!</p>
    
    </div>
    <hr>
    <div class="row">
      
      <div class="my-people" >
        <Pagination />
        <MyTestimonials/>
        
    </div>
    </div>
    
    </div>
    
  </section>
      
      
  
</template>

<script>
import MyTestimonials from '../components/MyTestimonials.vue'
import Pagination from '../components/Pagination.vue'


export default {
  components: {MyTestimonials, Pagination},
  data(){
    return {

    }
  }
}
</script>

<style scoped>
 
  img {
  
  object-fit: cover;
}

.card {
  width: calc((100% / 4) - 15px);
  min-width: 300px;
  order: 0.25px solid rgb(221, 216, 216);
  border-radius: 10px;
  padding: 10px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  
} 
.my-people {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;

}
.heading {
  width: 150px;
  height: 2px;
  background: #42b983;
  border-radius: 5px;
  margin-left: 30px;
  margin-bottom: 30px;
}


</style>