<template>
  <div class="main-container">
    <Sidebar :opened="opened" :toggleMenu='toggleMenu'/>
  </div>
   
  <main :class="{viewopen: opened}">
    <router-view/>
  </main>

  
  
</template>
<script>
// import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
export default {
  components: {
    // Navbar
    Sidebar
  },
 data(){
    return {
      opened: false
    }
  },
  methods: {
    toggleMenu(){
      this.opened = !this.opened
    }
  }

}
</script>
<style>

:root{
  --skin: #42b983;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

 #nav a {
  font-weight: bold;
  color: #2c3e50;
  font-size: 16px;
}

#nav a:hover{
  color: #42b983;
}

#nav li a.router-link-active {
  color: #42b983;
} 

html, body,{
  background: #eee;
  margin: 0;
  line-height: 1.5;
  font-family: "Montserrat", sans-serif;
  font-weight: 400;
  color: #2c3e50;
  font-size:16px;
}
* {
  margin: 0;
  padding: 0;
  outline: none;
  text-decoration: none;
  box-sizing: border-box;
}
.view {
    margin-left: 280px;
    transition: all 0.3s linear; 
    height: 100vh;
    padding: 25px;
    text-align: start;
  }
  main{
    transition: all 0.3s linear;
  }
.view h1 {
    
    padding: 60px 0 70px ;
  }
@media screen and (max-width:1200px) {
  body {
    line-height: 1.2;
    font-weight: 350;
  }
  .view {
    margin-left:0 ;
  }

  main.viewopen {
    margin-left: 280px;
  }
}

</style>
