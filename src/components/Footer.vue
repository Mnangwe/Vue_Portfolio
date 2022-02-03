<template>
  <div class="footer">
     <p class="text">
         Copyrights &copy; reserved |
     </p>
     <p class="text">
        Created with love & care 
    </p>  
      <div class="item">
          <span style='font-size:24px;'>&#128153;</span>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.item {
    display: none;
}
    .footer {
        color: #fff;
    }
@media screen and (max-width: 1040px) {
    .text {
        display: none;
    }
    .item {
        display: block;
        transition: all 0.3s linear; 
        margin-left: 220px;

    }
}
</style>