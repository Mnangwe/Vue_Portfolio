<template>
<div class="row">
    <div class="cards-wrapper col-sm-6 col-md-4" v-for="project in projects" :key="project.id">
        <div class="card" style="height: 400px; margin: 5px; text-align: left;">
            
            <img :src="require(`../assets/images/projects/${project.image}`)" class="card-img-top" alt="" height="250">
            <div class="info">
                <h4>
                 <strong>{{project.title}}</strong> 
                  <hr>
                  </h4>

            <p>
                {{project.description}}
                
            </p>
            <hr>
            <div class="links">
               <a :href="project.netlify" class="button" title="Live Code" target="_blank"><i class="fa fa-eye"></i></a>
              
               <!-- <a :href="project.gitHub" class="coding" title="github" target="_blank"><i class="fa fa-github"></i></a> -->
              
            </div>
            </div>
        </div>
    </div>
</div>
    
</template>

<script>
export default {
    name: 'Work',
    data() {
      return {
        projects: [
          {
            id:1,
            image:"reaction-timer.jpg",
            title: "Reaction Timer",
            gitHub: "https://github.com/Mnangwe/Reaction_timer",
            netlify: "https://reaction-time-aza.netlify.app",
            description:`Vue-3 project, a game that returns time depending how fast you reacted to click on the box.`
          },
          {
            id:2,
            image:"calculator.jpg",
            title: "Calculator",
            gitHub: "https://github.com/Mnangwe/JS_Calculator",
            netlify: "https://aza-calculator-pupuma.netlify.app",
            description:`Basic Vanilla Javascript Calculator with basic Math operators.`
          },
          {
            id:3,
            image:"book-ecommerce.jpg",
            title: "Book Store",
            gitHub: "https://github.com/Mnangwe/Book_Store",
            netlify: "https://book-e-commerce.netlify.app",
            description:`A book store created with Javascript using LocalStorage to store data and perform CRUD opperations.`
          },
          {
            id:4,
            image:"project1.jpg",
            title: "Random User Search",
            gitHub: "https://github.com/Mnangwe/Vue_CDN-RandomUser",
            netlify: "https://random-user-fetch-api.netlify.app",
            description:`Vue CDN using fetch function to fetch data of a random user on an API.`
          },
          {
            id:5,
            image:"stopwatch.jpg",
            title: "Stopwatch",
            gitHub: "https://github.com/Mnangwe/stopwatch-freeCodeCamp",
            netlify: "https://azabenathi-stopwatch.netlify.app/",
            description:`Work in progress-time-project. Stopwatch created with JavaScript and HTML only, in future we will add timer and worl clock`
          },
          {
            id:6,
            image:"ageTempCalculator.jpg",
            title: "Age & Temperature calculator",
            gitHub: "https://github.com/Mnangwe/age-temp-calculator",
            netlify: "https://aza-age-temp.netlify.app/",
            description:`Work in progress. JavaScript project to calculator the age using current time and converting temperature from Celsius to Fahrenheit`
          },
        ]

        
      }
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
a {
  color: inherit;
}
.card:hover {
  color: #000;
  
  background: #000;
  transition: all 0.3s ease-in-out;
}
.card {
  width: 280px;
  height: 360px;
  border-radius: 15px;
  padding: 1.5rem;
  background: white;
  position: relative;
  display: flex;
  align-items: flex-end;
  transition: 0.4s ease-out;
  box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.5);
  color: #000;
}
.card:hover {
  transform: translateY(20px);
}
.card:hover:before {
  opacity: 1;
}
.card:hover .info {
  opacity: 1;
  transform: translateY(0px);
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
  z-index: 2;
  transition: 0.5s;
  opacity: 0;
}
.card img {
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
     object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  border-radius: 15px;
}
.card .info {
  position: relative;
  z-index: 3;
  color: white;
  opacity: 0;
  transform: translateY(30px);
  transition: 0.5s;
}
.card .info h1 {
  margin: 0px;
}
.card .info p {
  letter-spacing: 1px;
  font-size: 18px;
  margin-top: 8px;
}
.card .info .button, .coding{
  padding: 0.6rem;
  left: 0;
  bottom: 0;
  outline: none;
  border: none;
  border-radius: 50%;
  background: white;
  color: black;
  font-weight: bold;
  cursor: pointer;
  transition: 0.4s ease;
  margin: 2px;
}

.card .info .button:hover {
  background: #42b983;
  color: white;
}
.links {
  display: flex;
  /* justify-content: space-evenly; */
  justify-content: end;
}

</style>
