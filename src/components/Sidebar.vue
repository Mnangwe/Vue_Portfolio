<template>
  <div class="d-flex flex-column side-bar flex-shrink-0 p-3 text-dark bg-light side" :class="{navbaropen: opened}" >
    
      <div class="logo">
        <a href="/" class="d-flex align-items-center text-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none" >
        
          Azabenathi
        </a>
      </div>
   
    <div class="nav-toggler" @click="toggleMenu()">
      <span></span>
    </div>
    <!-- <hr class="first-line"> -->
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
  components: { Footer },
  props: ['opened', 'toggleMenu']
}
</script>

<style>
.side .logo {
  padding: 30px 0;
  
}

.side .logo a {
  font-size: 40px;
  color: #2c3e50 !important;
  font-family: "Rubik", sans-serif;
  font-weight: 700;
  text-decoration: none;
  display: inline-block;
  position: relative;
  padding: 0 10px;
  line-height: 50px;
}

.side .logo a::before {
  content: "";
  height: 20px;
  width: 20px;
  position: absolute;
  margin: -2px;
  top: 0;
  left: 0;
}
.side .logo a::before{
  border-left: 4px solid var(--skin);
  border-top: 4px solid var(--skin)
}

::before, ::after {
    box-sizing: border-box;
}
.side .logo a::after {
  content: "";
  height: 20px;
  width: 20px;
  position: absolute;
  margin: -2px;
  bottom: 0;
  right: 0;
}
.side .logo a::after {
  border-bottom: 4px solid var(--skin);
  border-right: 4px solid var(--skin);
}

.side .nav-toggler {
  height: 40px;
  width: 45px;
  border: 1px solid #d4d4e3;
  cursor: pointer;
  position: fixed;
  right: 300px;
  top: 20px;
  z-index: 11;
  border-radius: 5px;
  background-color: #fdf9ff;
  display: none;
  -ms-flex-align: center;
  align-items: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  display: none;
}
.side .nav-toggler span {
  height: 2px;
  width: 18px;
  display: inline-block;
  position: relative;
  background: var(--skin);
}
.side .nav-toggler span::before {
  content: "";
  height: 2px;
  width: 18px;
  position: absolute;
  top: -6px;
  left: 0;
  background: var(--skin);
}
.side .nav-toggler span::after {
  content: "";
  height: 2px;
  width: 18px;
  position: absolute;
  top: 6px;
  left: 0;
  background: var(--skin);
}
.side .nav {
  list-style: none;
  margin: 70px 0;
  padding: 0;
}
.side {
  width: 280px;
  background-color: #fdf9ff;
  position: fixed;
  height: 100%;
  left: 0;
  top: 0;
  z-index: 10;
  border-right: 1px solid #e8dfec;
  padding: 30px;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  
}

.head {
    text-align: center;
    color: #2c3e50;
}


@media screen and (max-width: 1200px) {
  .side .nav-toggler{
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    right: 30px;
  }
  .side {
    left: -100%;
  }
  
  .navbaropen {
  width: 270px;
  background-color: #fdf9ff;
  position: fixed;
  height: 100%;
  left: 0;
  top: 0;
  z-index: 10;
  border-right: 1px solid #e8dfec;
  padding: 30px;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  }
  .viewopen {
    margin-left: 280px;
    transition: all 0.3s linear; 
    height: 100vh;
    padding: 25px;
    text-align: start;
  }
  .viewopen h1 {
    
    padding: 60px 0 70px ;
  }
}    

</style>

