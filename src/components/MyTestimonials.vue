<template>
  <div class="row">
    <div class="my-people cards-wrapper col-md-6 col-lg-4" v-for="testimony in testimonials" :key="testimony.id">
        <div class="card">
            <div class="image-card">
                <img :src="require(`../assets/images/profiles/${testimony.image}`)" class="card-img-top" alt="">
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
</template>

<script>
export default {
    name:'MyTestimonials',
    data(){
        return {
            testimonials: [
                {
                    id:1,
                    fname: "Alex Sexwale",
                    title: "Lecturer",
                    email: "alex@lifechoices.co.za",
                    content: `He is an oustanding developer who goes 
                             the extra mile to completing beyond what is required 
                             by him. He will assist his peers when they are struggling 
                             and wants to demonstrate what he has just learnt.`,
                    image:"Alex.jpg"
                },
                {
                    id:2,
                    fname: "Jason Wandrag",
                    email: "jason@lifechoices.co.za",
                    content: `Azabenathi has already developed a programmer mindset and 
                            is always learning as much as he can. He has also shown to work 
                            extremely well in teams and transforms into a natural leader. 
                            Azabenathi is well on his way to becoming a great developer.`,
                    title:"Lecturer",
                    image:"Json.jpg"
                },
                {
                    id:3,
                    fname: "Godwin Dzvapatsva",
                    email: "godwin@lifechoices.co.za",
                    content: `Seldom have I been able to recommend someone without reservation. 
                             It is my pleasure to do so in the case of Azabenathi Pupuma for any IT 
                             organisation. Azabenathi has a strong passion for coding and his attention 
                             to detail is exceptional. Azabenathi is one of our finest and most well-rounded 
                             student at Lifechoices Academy.`,
                    title:"Head of Curriculum & Learning",
                    image:"godwin-2022.jpg"
                },
                {   id:4,
                    fname: "Nomvuyiseko Mpofu",
                    email: "nomvuyisekompofu@gmail.com",
                    content: `Azabenathi is a very creative developer, 
                             he has so far produced the best work in class. 
                             His work ethic is impressive and he always goes out of his way to help 
                             others. I love his working style, he is driven and dedicated.`,
                    title:"Collegue & Front-end Developer",
                    image:"Nomvuyiseko.jpg"
                },
                {
                    id:5,
                    fname: "Kagiso Mphayi",
                    email: "mphayi96@gmail.com",
                    content: `Azabenathi is a Hard working individual who's 
                             always eager to expand his knowledge. He likes helping people 
                             and he is a great leader as well.`,
                    title:"Collegue & Full-stack Developer",
                    image:"Kagiso.jpg"
                },
            ]
        }
    }
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
        height: 620px;
        text-align: justify;
        border-radius: 20px;
    }
    .image-card img {
        height: 250px;
        object-fit: cover;
        border-radius: 20px 20px 0 0;
    }
    .card-text {
        height: 200px;
    }
    @media screen and (max-width: 1400px) {
    p.card-text {
        height: 196px;
        overflow: hidden;
  }
}
</style>