 <template><head>
    <meta charset="UTF-8">
 <meta name="viewport" Content="width=device-width,initial-scale=1.0">
 
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.1/css/all.css" integrity="sha384-vp86vTRFVJgpjF9jiIGPEEqYqlDwgyBgEF109VFjmqGmIY/Y4HV4d3Gp2irVfcrp" crossorigin="anonymous">
    <link rel="preconnect" href="https://fonts.gstatic.com">
 <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
 <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<HomePage />
<VNutrition />
<FooterComp /> 
  
</template>

<script>

 
 import HomePage from './components/HomePage.vue'
 import FooterComp from './components/FooterComp.vue'
 import VNutrition from './components/VNutrition.vue'


export default {
  name: 'App',
  components: {
    VNutrition,HomePage,
    FooterComp,
    
    
  },
}
</script>

<style>
#App{
  text-align: center;
}
html, body {width: auto!important; overflow-x: hidden!important} 
</style>
