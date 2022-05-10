<template>
<!-- <head>
    <meta charset="UTF-8">
 <meta name="viewport" Content="width=device-width,initial-scale=1.0">
 
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.1/css/all.css" integrity="sha384-vp86vTRFVJgpjF9jiIGPEEqYqlDwgyBgEF109VFjmqGmIY/Y4HV4d3Gp2irVfcrp" crossorigin="anonymous">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    </head> -->
 <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/css/bootstrap.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css">
<!-- <body>
    <nav class="ttt"> -->
<marquee width="100%" direction="right" height="30px">
Don't focus on how much you eat. Focus on what you eat

</marquee>
        
            
       <div class="o">
        <h1>Welcome to Nutrients Check</h1> </div>
        <div class="qwe">
         <div class="mmm">
        <input typesearch v-model ="search1" class="search" placeholder="enter the food"/><br>
           </div>
        
        <button @click="getSearch">search</button><br><br><br><br>
         
        <div  v-if=" this.search && nutrients.calories!='0'&& this.err ==''">
            <div class="b">
  <h4>
                CALORIES: {{nutrients.calories}}</h4>
            
        
       <div>
        <h4>TOTALWEIGHT: {{nutrients.totalWeight}}gms </h4> 
       </div> 
        <div>
           <h4 v-for="l in get_response.dietLabels" :key="l">
           {{removeUnderscore(l)}}
        </h4>
        
        </div> 
        </div> 
    
        
                 
          </div> 
       
<div class="we" v-else-if="this.err!==''">
    ENTER SOMETHING</div>
    <div class="w" v-else-if="this.nutrients.calories==0">enter valid info</div><br>
  
  
    <CardComp /> 
    </div>
    <!-- </nav>
</body> -->
</template>

<script>
import Axios from 'axios';
 import CardComp from './CardComp.vue'

    export default {
        name: 'VNutrients',
        components:{
             CardComp,
        },
        data () {
        return {
           
            nutrients: {},
             search:false,
             search1:'',
            
            err:'',
            get_response:{}

        }
    },
        methods: {
         getSearch() {
        Axios.get('https://api.edamam.com/api/nutrition-data?app_id=a3d8ef0d&app_key=c260a2ce7f82409710ede374215aa455&nutrition-type=logging&ingr=' + this.search1).then(response =>{
              
              console.log(response.data)
             this.nutrients =response.data;
             this.get_response=response.data;
             this.search=true;
            
             }).catch((err) => {

          this.loading = false;

          this.err = "Something went Wrong";

          console.log("Error", err);

        
    });     
      
    } ,
     removeUnderscore (label) {
            var newLabel=  label.replaceAll('_',' ');
            return newLabel;}
    },
    
}
</script>
<style>
.qwe {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: auto;
  background: #2c3e50;
  background-image: url('../assets/t.jpg');
 
   height: auto;
   width:auto;
   color: black;
   
}
.mmm{
    
    margin-bottom: 20px ;
    text-align: center;
    color: red;
    
  
}
.mmm .search{
    width: 50%;
    
    color: black;
    padding:10px 30px;
    appearance: none;
    border:none;
    outline: none;
    background: none;
    box-shadow: 0px 0px 8px rgba(0, 0,0, 0.25);
    background-color: silver;
    border-radius:0px 10px 0px 10px ;
    transition:0.4s;
    align-items: center;
  margin-top: 50px;
      
}
.mmm.search.button
{
background: skyblue;

}
#v-if{
    color: blue;
    
    
}
button{
    background:  darkgray;
}
marquee{
    color: blue;
    font-size: 130%;
    border-bottom: 5px solid black;
    
}
.b{
border:10px solid maroon;

width: 300px;
height: 200px;
margin: 0 40%;
border-radius: 80px;
background: moccasin;
}
.o{
    text-align: center;
    color: brown;
    
}
.we{
    border:10px solid maroon;

width: 140px;
height: 100px;
margin: 0 45%;
border-radius: 90px;
background: moccasin;

}
 .w{
    border:10px solid maroon;

width: 140px;
height: 70px;
margin: 0 45%;
border-radius: 90px;
background: moccasin;

}


/* 
[class*="col-"]{
  width: 100%;
}
@media only screen and (min-width:600px){
  .col-1{width:8.33%;}
  .col-1{width:16.66%;}
  .col-1{width:25%;}
  .col-1{width:33.33%;}
  .col-1{width:41.66%;}
  .col-1{width:50%;}
  .col-1{width:58.33%;}
  .col-1{width:66.66%;}
  .col-1{width:75%;}
  .col-1{width:83.33%;}
  .col-1{width:91.66%;}
  .col-1{width:100%;}

}
  @media only screen and (min-width:768px){  
  .col-1{width:8.33%;}
  .col-1{width:16.66%;}
  .col-1{width:25%;}
  .col-1{width:33.33%;}
  .col-1{width:41.66%;}
  .col-1{width:50%;}
  .col-1{width:58.33%;}
  .col-1{width:66.66%;}
  .col-1{width:75%;}
  .col-1{width:83.33%;}
  .col-1{width:91.66%;}
  .col-1{width:100%;}

} */
/* @media screen and (max-width: 768px) {
  .ttt {
    flex-direction: column;
    align-items: flex-start;
    padding: 10px 24px;
  }} */
</style>