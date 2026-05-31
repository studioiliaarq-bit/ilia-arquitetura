<template>
  <div id="coupons">
    <span v-if="show">Cupom cópiado!</span>
    <div v-for="(item, index) in coupons" :key="index" class="card">
      
      <h3>{{ item.nome }}</h3>
      
      <p>
        Cupom: 
        <strong @click="copiarCupom(item.coupon)">
            {{ item.coupon }}
        </strong>
      </p>
      
      <a :href="item.link" target="_blank">
        🔗 Acessar site
      </a>

    </div>

  </div>
</template>


<script>


export default {
  name: 'Coupons',

  components: {

  },

    data() {
        return {
            show: false,
            coupons: [

            {
                nome: 'Westwing',
                link: 'https://www.westwing.com.br/',
                coupon: 'MAGDANASCIMENTOWW'
            },

            ]
        }
    },
    methods: {
        showMessage() {
          this.show = true;

          if(this.show == true) {

            setTimeout(() => {     
               this.show = false; 
            }, 4000)

          }

        },
        copiarCupom(cupom) {
            navigator.clipboard.writeText(cupom)
            .then(() => {
                console.log('Cupom copiado:', cupom);
                if(this.show == false) {
                  this.showMessage();
                }                 
            })
            .catch(err => {
                console.error('Erro ao copiar:', err);
            });
        }
    },

}
</script>

<style scoped>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: var(--color-7);
}

#coupons {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
  padding: 0 0 250px 0;
}

.card {
  background-color: var(--color-1);
  text-align: center;
  opacity: 0.9;  
  padding: 15px;
  border-radius: 10px;
  width: 40%;
  
}

.card p {
    margin: 5px 0;
}

.card a {
  text-decoration: none;
}

strong, a {
    cursor: pointer;
}

strong:hover, a:hover {
    color: var(--color-4);
    transition: 1,5s;
}

@media (max-width: 768px) {
   .card {
    width: 90%;
   } 
}


span {
  background-color: var(--color-1);
  color: var(--color-7);
  width: 150px;
  text-align: center;
  opacity: 1;
  border-radius: 4px;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  animation: message-animation 3s ease-in;
  animation-delay: 0s;
  animation-fill-mode: forwards;
  z-index: 99;
}

@keyframes message-animation {
  0%{
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}


  
</style>

