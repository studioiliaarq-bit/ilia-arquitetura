<template>
  <div id="container-coupons">  
     <div id="box-polygon">   
      <PolygonAnimation />      
    </div>
    <Coupons />
    <Footer />
  </div>
</template> 


<script>
import PolygonAnimation from '@/components/PolygonAnimation.vue';
import Coupons from '@/components/Coupons.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'CouponsView',

  components: {
    PolygonAnimation, 
    Coupons,
    Footer,
  },

}
</script>

<style scoped>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#container-coupons {
  background-image: url('../assets/concept-image.webp'); 
  background-repeat: no-repeat;
  background-size: cover;  
  width: 100%;
  height: auto;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  z-index: 99;
}

@media (max-width: 980px) {
  #container-coupons {
    background-image: url('../assets/apartamento-terra/cozinha/1.webp');
    background-repeat: no-repeat;
    background-size: cover;  
  }
}

#box-polygon { 
  width: 100%;
  height: auto;  
  margin: 80px 0;
  display: flex;
  justify-content: center;
  align-items: center; 
  z-index: 100;

}


  
</style>

