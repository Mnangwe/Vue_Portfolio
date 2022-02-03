<template>
  <div class="d-flex flex-column side-bar flex-shrink-0 p-3 text-dark bg-light">
    <div class="logo">
      <a href="/" class="d-flex align-items-center text-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none">
      
       <img src="../assets/logo.png" alt="" class="logo-image">
    </a>
    </div>
     
    <hr class="first-line">
    <ul class="nav nav-pills flex-column mb-auto text-start" id="nav">
      <li class="nav-item" title="Home">
        <router-link to="/" href="#" class="nav-link " aria-current="page">
          <i class='fas fa-home me-2' ></i> 
          Home
          <hr class="icon">
        </router-link>
      </li>
      <li class="nav-item" title="About">
        <router-link to="/about" href="#" class="nav-link">
          <i class='fas fa-user me-2' ></i>  
          About
          <hr class="icon">
        </router-link>
      </li>
      <li class="nav-item" title="Projects">
        <router-link to="/projects" href="#" class="nav-link">
          <i class='fas fa-th-large me-2' ></i> 
          Projects
          <hr class="icon">
        </router-link>
      </li>
      <li class="nav-item" title="Testimonials">
        <router-link to="/testimonials" href="#" class="nav-link">
          <i class='fas fa-user-circle me-2'></i> 
          Testimonials
          <hr class="icon">
        </router-link>
      </li>
      <li class="nav-item" title="Contact">
        <router-link to="/contact" href="#" class="nav-link">
          <i class='fas fa-comments me-2'></i> 
          Contact
          <hr class="icon">
        </router-link>
      </li>
    </ul>
    <hr class="icon text-white">
        
        <Footer />
  </div>
  
</template>

<script>
import Footer from './Footer.vue'
export default {
  name:"Sidebar",
  components: { Footer }
}
</script>

<style>

.side-bar {
  height: 100vh;
  width: 280px;
  left: 0;
  top: 0;
  bottom: 0;
  position: fixed;
  transition: all 0.3s linear;
  background: #2c3e50 !important;
}
.logo-image {
  top: 0;
  left: 0;
  width: 250px;
  height: 250px;
  background: #2c3e50;
  border-radius: 50%;
}

.head {
    text-align: center;
    color: #2c3e50;
}

.mobile-nav {
  position: fixed;
  top: 20px;
  right: 20px;
  display: none;
}

 @media screen and (max-width: 920px) {
    .logo-image {
      display: none;
    }
    
  }

</style>