<template>
  <div class="main-container">
    
    <Sidebar :opened="opened" :toggleMenu='toggleMenu'/>
    
    
    <main class="main-content" :class="{viewopen: opened}">
      <router-view/>
    </main>
  </div>

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
main{
    transition: all 0.3s linear;
  }
section {
  background-color: #f2f2fc;
  min-height: 100vh;
  display: block;
  padding: 0 30px;
  position: fixed;
  left: 280px;
  top: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
  overflow-x: hidden;
  overflow-y: inherit;
  opacity: 1;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
.section-title {
  font-family: "Rubik", sans-serif;
  padding-left: 15px;
  padding-right: 15px;
  flex: 0 0 100%;
  max-width: 100%;
  margin-bottom: 60px;
}
.section-title h2 {
  font-size: 40px;
  color: #302e4d;
  font-family: "Rubik", sans-serif;
  font-weight: 700;
  margin: 0;
  position: relative;
  
}
.section-title h2::before {
  content: "";
  height: 4px;
  width: 75px;
  position: absolute;
  top: 100%;
  left: 2%;
  margin-left: -8px ;
  margin-top: 2px;
  background-color: var(--skin);
}
.section-title h2::after {
  content: "";
  height: 4px;
  width: 100px;
  position: absolute;
  top: 100%;
  left: 2%;
  margin-left: -8px ;
  margin-top: -6px;
  background-color: var(--skin);
}

main{
  transition: all 0.3s linear;
}

section .container {
  padding-top: 60px;
  padding-bottom: 70px;
  text-align: left !important;
}

.container{
    max-width: 1100px;
    width: 100%;
    margin: auto;
}

@media screen and (max-width:1200px) {
  body {
    line-height: 1.2;
    font-weight: 350;
  }
  section {
    left:0 ;
  }

  main.viewopen section{
    left: 280px;
  }
}

</style>
