<template>
  <div class="testimonial view">
    <div class="container">
      <div class="row d-flex" style="flex-direction: column">
        <h3 class="display-6">Testimonials</h3>
        <div class="heading"></div>
      </div>
    <hr>
    <div class="row">
      <p class="muted">Look at what my lovely colleagues, lecturers and friends have to say about me!</p>
    
    </div>
    <hr>
    <div class="row">
      <div class="my-people">
      <MyTestimonials/>
    </div>
    </div>
    
    </div>
    
  </div>
      
      
  
</template>

<script>
import MyTestimonials from '../components/MyTestimonials.vue'


export default {
  components: {
    
    MyTestimonials

    },
  data(){
    return {

    }
  }
}
</script>

<style scoped>
  .container {
  text-align: start;
  margin: auto;
  padding: 60px 0 70px;
}
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