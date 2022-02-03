<template>
  
   <Sidebar />
  
  <router-view/>

  
  
</template>
<script>
// import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
export default {
  components: {
    // Navbar
    Sidebar
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav a {
  font-weight: bold;
  color: #fff;
  font-size: 16px;
}

#nav a:hover{
  color: #42b983;
}

#nav li a.router-link-active {
  color: #42b983;
}
html, body, .view {
  background: #eee;
}
.view {
    margin: 0 0 0 280px;
    transition: all 0.3s linear; 
    height: 100vh;
    padding: 25px;
    text-align: start;
  }
  .view h1 {
    
    padding: 60px 0 70px ;
  }

  @media screen and (max-width: 1040px) {
  .side-bar {
    left: -230px;
  }
  .side-bar.active {
    left: 0px;
  }
  .view {
    margin-left: 50px;
  }
  .mobile-nav {
    display: block;
  }
  .fas{
    margin-left: 210px;
    transform: scale(1.5);
  }
  .home.view {
    padding: 220 120px !important;
  }
  .logo {
    display: none;
  }
}
</style>
