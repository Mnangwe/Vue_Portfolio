<template>
  <form @submit="submitForm" action="https://formspree.io/f/mqknploe"
  method="POST" target="_blank">
    <div class="row">
        <div class="col-xs-12 col-md-6">
            <label>Full Name: </label>
            <input type="text"  name="name" id="" v-model="fname" required>
        </div>
        <div class="col-xs-12 col-md-6">
            <label>Email: </label>
            <input type="email" name="email" id="" v-model="email" required>
        </div>
    </div>
    <label>Message length:</label>
    <div class="message">
        <textarea name="message" id="" cols="" v-model="message" rows="5"></textarea>
    </div>
    <div class="submit">
        <button @click="submitData">Send Me</button>
    </div>
      
  </form>
</template>

<script>


export default {
    data(){
        return {
            fname:"",
            email:"",
            message:""
        }
    },
     
}
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
    label {
        color: #2c3e50;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.8em;
        text-transform: uppercase;
        letter-spacing: 1.7px;
        font-weight: bold;
    }
    input, select, textarea {
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
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