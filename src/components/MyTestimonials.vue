<template>
  <div class="row" v-if="testimonials" id="cards">
    <div class="my-people cards-wrapper col-md-6 col-lg-4" v-for="testimony in testimonials" :key="testimony.id" >
        <div class="card">
            <div class="image-card">
                <img :src="testimony.image" class="card-img-top" alt="">
            </div>
            <div class="card-body">
                <p class="title secondary">{{testimony.fname}} - <em>{{testimony.title}} </em></p>
                <p class="card-text">{{testimony.content}}</p>
                <hr>
                <p class="email">{{testimony.email}} </p>
                <hr>
            </div>
        </div>
    </div>
    
    
  </div>
  <div v-else>
      <SpinLoader />
  </div>
  
</template>

<script>
import SpinLoader from './SpinLoader.vue'

export default {
    name:'MyTestimonials',
    components: {SpinLoader},
    
    data(){
        return {
          testimonials: null,
          
        }
    },
    
    mounted() {
      fetch('https://portfolio-api-aza.herokuapp.com/testimonials')
        .then(res => res.json())
        .then(data => {
          this.testimonials = data
          console.log(data)
          console.log(this.testimonials)
          
          })
        .catch(err => console.log(err.message))

        
    
    },
}
</script>
    
<style scoped>
    .my-people {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        margin: 10px 0;
    }
    .card {
        height: 600px;
        text-align: justify;
        border-radius: 20px;
    }
    .card:hover {
        -webkit-transition: all 0.3s ease;
        transition: all 0.3s ease-in-out;
        transform: scale(1.2);
        z-index: 1;
    }
    .card:hover img {
        height: 180px;
        -webkit-transition: all 0.3s ease;
        transition: all 0.3s ease-in-out;
    }
    .card:hover .card-text {
        height: 240px;
        -webkit-transition: all 0.3s ease;
        transition: all 0.3s ease-in-out;
    }
    .image-card img {
        height: 250px;
        object-fit: cover;
        border-radius: 20px 20px 0 0;
    }
    .card .title, .card .email {
        font-weight: bold;
    }
    .card-text {
        height: 180px;
        object-fit: cover;
        font-size: 14px;
    }
    @media screen and (max-width: 1400px) {
    p.card-text {
        height: 196px;
        overflow: hidden;
  }
}
</style>