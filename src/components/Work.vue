<template>
<div class="container" v-if="projects">
  
    <div class="cards-wrapper" v-for="project in projects" :key="project.id">
        <div class="card bg-dark shadow-dark" style=" margin: 5px; text-align: left;">
            <div class="project-image">
              <img :src="project.image" class="card-img-top" :alt="project.title">
            </div>
            
            <div class="info">
                <h4>
                 <strong>{{project.title}}</strong> 
                  <hr>
                  </h4>

            <!-- <p>
                {{project.description}}
                
            </p>
            <hr> -->
                <div class="links">
                  <div class="icon1">
                    <a :href="project.netlify" class="button" title="Live Demo" target="_blank"><i class="fa fa-eye"></i></a>
                  </div>
                  <div class="icon2">
                     <a :href="project.gitHub" class="coding git" title="Code" target="_blank"><span class="iconify" data-icon="brandico:github"></span></a>
                  </div>
                  
                  
                  <!-- <a :href="project.gitHub" class="coding" title="github" target="_blank"><i class="fa fa-github"></i></a> -->
                  
                </div>
            </div>
        </div>
    </div>
  </div>
    
<div v-else class="loader">
  <SpinLoader />
</div>


    
</template>

<script>
import SpinLoader from './SpinLoader.vue'

export default {
    name: 'Work',
    components: {SpinLoader},
    data() {
      return {
        projects: null
        // projects: [
        //   {
        //     id:1,
        //     image:"reaction-timer.jpg",
        //     title: "Reaction Timer",
        //     gitHub: "https://github.com/Mnangwe/Reaction_timer",
        //     netlify: "https://reaction-time-aza.netlify.app",
        //     description:`Vue-3 project, a game that returns time depending how fast you reacted to click on the box.`
        //   },
        //   {
        //     id:2,
        //     image:"calculator.jpg",
        //     title: "Calculator",
        //     gitHub: "https://github.com/Mnangwe/JS_Calculator",
        //     netlify: "https://aza-calculator-pupuma.netlify.app",
        //     description:`Basic Vanilla Javascript Calculator with basic Math operators.`
        //   },
        //   {
        //     id:3,
        //     image:"book-ecommerce.jpg",
        //     title: "Book Store",
        //     gitHub: "https://github.com/Mnangwe/Book_Store",
        //     netlify: "https://book-e-commerce.netlify.app",
        //     description:`A book store created with Javascript using LocalStorage to store data and perform CRUD opperations.`
        //   },
        //   {
        //     id:4,
        //     image:"project1.jpg",
        //     title: "Random User Search",
        //     gitHub: "https://github.com/Mnangwe/Vue_CDN-RandomUser",
        //     netlify: "https://random-user-fetch-api.netlify.app",
        //     description:`Vue CDN using fetch function to fetch data of a random user on an API.`
        //   },
        //   {
        //     id:5,
        //     image:"stopwatch.jpg",
        //     title: "Stopwatch",
        //     gitHub: "https://github.com/Mnangwe/stopwatch-freeCodeCamp",
        //     netlify: "https://azabenathi-stopwatch.netlify.app/",
        //     description:`Work in progress-time-project. Stopwatch created with JavaScript and HTML only, in future we will add timer and worl clock`
        //   },
        //   {
        //     id:6,
        //     image:"ageTempCalculator.jpg",
        //     title: "Age & Temperature calculator",
        //     gitHub: "https://github.com/Mnangwe/age-temp-calculator",
        //     netlify: "https://aza-age-temp.netlify.app/",
        //     description:`Work in progress. JavaScript project to calculator the age using current time and converting temperature from Celsius to Fahrenheit`
        //   },
        // ]

        
      }
    },
    mounted() {
      fetch('https://portfolio-api-aza.herokuapp.com/projects')
        .then(res => res.json())
        .then(data => {
          this.projects = data
          console.log(data)
          console.log(this.projects)
          
          })
        .catch(err => console.log(err.message))
    }
}
</script>

<style scoped>

    @import url('https://fonts.googleapis.com/css?family=Heebo:400,700|Open+Sans:400,700');

:root {
  --color: #3c3163;
  --transition-time: 0.5s;
}
h4.title {
    border-bottom: 2px solid #3c3163;
}
.container {
  display: flex;
  flex-wrap: wrap;
}
a {
  color: inherit;
}
.card:hover {
  color: #000;
  
  background: #000;
  transition: all 0.3s ease-in-out;
}
.card {
  width: 300px;
  height: 200px !important;
  border-radius: 10px;
  padding: 15px;
  background: white;
  position: relative;
  display: flex;
  align-items: flex-end;
  transition: 0.4s ease-out;
  box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.5);
  color: #000;
  border: 6px solid #fdf9ff;
  overflow: hidden;
  cursor: pointer;
}

.shadow-dark {
  -webkit-box-shadow: 0 0 20px rgb(48 46 77 / 15%);
  box-shadow: 0 0 20px rgb(48 46 77 / 15%);
}

.project-image img {
  width: 100%;
  display: block;
}

.card:hover:before {
  opacity: 1;
}
.card:hover .info {
  opacity: 1;
  /* width: 100%;
  height: 100%; */
}
.card:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 100%;
  border-radius: 15px;
  background: rgba(0, 0, 0, 0.6);
  z-index: 1;
  transition: 0.5s;
  opacity: 0;
}
.card img {
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: scale-down !important;
  position: absolute;
  top: 0;
  left: 0;
  border-radius: 15px;
}
.card .info {
  position: absolute;
  top: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.8);
  height: 100%;
  width: 100%;
  z-index: 1;
  padding: 30px;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  color: white;
  opacity: 0;
  
}
.card .info h4 {
  font-size: 18px;
  font-weight: 700;
  color: #ffffff;
  text-transform: capitalize;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  -webkit-transform: translateX(-20px);
  transform: translateX(-20px);
  opacity: 0;
}
.card:hover .info h4 {
  -webkit-transform: translateX(0px);
  transform: translateX(0px);
  opacity: 1;
}

.icon1 .button{
  height: 30px;
  width: 30px;
  background-color: #ffffff;
  color: red;
  text-align: center;
  border-radius: 50%;
  position: absolute;
  opacity: 0;
  -webkit-transition: all 0.4s ease;
  transition: all 0.4s ease;
  right: 30px;
  bottom: 30px;
  transform: translateX(20px);
  -webkit-transform: translateX(20px);
}
.icon2 .coding {
  height: 30px;
  width: 30px;
  background-color: #ffffff;
  color: red;
  text-align: center;
  border-radius: 50%;
  position: absolute;
  opacity: 0;
  -webkit-transition: all 0.4s ease;
  transition: all 0.4s ease;
  left: 30px;
  bottom: 30px;
  transform: translateX(-40px);
  -webkit-transform: translateX(-40px);
}
.card:hover .icon1 .button, .icon2 .coding {
  -webkit-transform: translateX(0px);
  transform: translateX(0px);
  opacity: 1;
}
.links {
  display: flex;
  justify-content: space-between;
  flex-direction: row-reverse;
}

</style>
