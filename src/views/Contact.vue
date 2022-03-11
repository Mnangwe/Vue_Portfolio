<template>
  <!-- <h1>Contact Me</h1> -->
  <section class="contact view" :class="{viewopen: opened}">
    <div class="container">
      <div class="row text-start section-title" style="">
        <h2 class="">Contact Me</h2>
        

      </div>
      <div class="row icon-display">
        <div class="col-sm-12 col-md-4">
          <i class="fas fa-mobile-alt icon"></i>
          <p>
            <strong>Call Me On:</strong><br />
            +27 60 910 9527 | 
            +27 76 844 5550
          </p>
      </div>
      <div class="col-sm-12 col-md-4">
          <i class="fas fa-map-marker-alt icon"></i>
          <p><strong>Home:</strong><br />City of Cape Town, WC, South Africa</p>
      </div>
      <div class="col-sm-12 col-md-4">
          <i class="fas fa-envelope icon"></i>
          <p><strong>Email:</strong><br />pupuma.azabenathi@gmail.com</p>
      </div>
    </div>
    <div class="row d-flex justify-content-center container">
      <div class="row">
        
      <Form/>
     
      </div>
    </div>
    </div>
  </section>
</template>

<script>
import Form from '../components/Form.vue'
export default {
  name: "Contact",
  components: { 
    Form 
    },
};
</script>

<style scoped>


.icon-display{
  margin: 20px 0;
  margin-top: 40px;
}
.fas.icon  {
  font-size: 48px;
  margin: 20px 0;
}
h3 {
  text-align: start;
  font-size: bolder;
}
.heading {
  width: 150px;
  height: 2px;
  background: #42b983;
  border-radius: 5px;
  margin-left: 30px
}
@media screen and (max-width: 768px) {
  .fas.icon {
    font-size: 20px;
  }
  
}
</style>
