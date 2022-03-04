<template>
  <form @submit.prevent="submitForm">
    <div class="row">
      <div class="col-xs-12 col-md-6">
        <label
          >Full Name: </label>
          <input type="text" name="name" id="" v-model="fname" required />
       
      </div>
      <div class="col-xs-12 col-md-6">
        <label
          >Company:</label>
          <input
            type="company"
            name="company"
            id=""
            v-model="company"
            required
          />
        
      </div>
    </div>

    <div class="row">
      <div class="col-xs-12 col-md-6">
        <label
          >Email:</label>
          <input type="email" name="email" id="" v-model="email" required />
        
      </div>
      <div class="col-xs-12 col-md-6">
        <label
          >Subject:</label>
          <input type="text" name="subject" id="" v-model="subject" required />
        
      </div>
    </div>

    <div class="row text-area">
      <label>Message:
        <div class="message">
          <textarea name="message" id="" cols="" v-model="message" rows="5"></textarea>
        </div>
      </label>
    </div>
        <!-- <p v-if="">
            {{response}}
        </p> -->
        
    <div class="submit">
      
       <p class="response text-primary">{{response}}</p> 
      <button type="submit" :disabled='isLoading'>Send Me</button>
    </div>
  </form>
</template>

<script>
import SpinLoader from './SpinLoader.vue'
export default {
  components: {SpinLoader},
  data() {
    return {
      fname: "",
      email: "",
      message: "",
      subject: "",
      company: "",
      response: "",
      isLoading: false,
    };
  },
  methods: {
    // submit the form to our backend api
    async submitForm() {
      this.isLoading = true
      const res = await fetch("https://portfolio-api-aza.herokuapp.com/contact", {
        method: "POST",
        headers: { "Content-Type": "application/json" },

        // pass in the information from our form
        body: JSON.stringify({
          fname: this.fname,
          email: this.email,
          message: this.message,
          subject: this.subject,
          company: this.company,
        }),
      })
      .then(res => res.json())
      .then(data => {
        console.log(data.msg)
        this.response = data.msg
        this.fname = "",
        this.email = "",
        this.message = "",
        this.subject = "",
        this.company = ""
      }).catch(err => console.log(err.message))
      .finally(() => {
        this.isLoading = false
      })
    },
  },
};
</script>

<style>
form {
  max-width: 600px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
  border: 1px solid #ddd;
}
.row {
    padding: 4px 30px !important;
}

label {
  color: #2c3e50;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.8em;
  text-transform: uppercase;
  letter-spacing: 1.7px;
  font-weight: bold;
}
input,
select,
textarea {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input:focus-visible,
select:focus-visible,
textarea:focus-visible{
    border: none;
    border-bottom: 1px solid #42b983;
}
button {
  background: #42b983;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}
.submit {
  text-align: center;
}
</style>