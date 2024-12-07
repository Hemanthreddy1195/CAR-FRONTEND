<template>
    <div class = "portfolio">
        <a href="https://gray-hmada4-live-8.tiiny.site/"><b>Visit My PortFolio</b></a>
    </div>

  <div class = 'Title'>
    <h1>
    Welcome To The
  </h1>
  <h1>
     New Haven Car Company
    </h1>
  </div>

  <div> 
    <CarGrid/>
  </div>
</template>

<script>
import CarGrid from "./CarGrid.vue"
export default {
  name: 'IndexPage',
  components:{
    CarGrid
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Title {
background-image: url('../assets/ferrari.jpg');
background-size:auto;
background-repeat: no-repeat; 
font-size: 5rem;
margin-left: 15%;
margin-right: 17%;
font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
font:bold;
color: white;
text-align: center;
padding-bottom: 25%;
margin-bottom: 3%;
text-shadow: 5px 5px 0px black;
box-shadow: rgb(38, 57, 77) 0px 20px 30px -10px;


}

.portfolio{
  background-color:rgb(38, 57, 77);
  padding-bottom: 1%;
  padding-top: 1%;
  color: white;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  font-weight: 500;
  font-size: 2rem;
  margin-bottom: 1%;
}
</style>
