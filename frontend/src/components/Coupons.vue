<template>
  <div id="coupons">
    
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
        copiarCupom(cupom) {
            navigator.clipboard.writeText(cupom)
            .then(() => {
                console.log('Cupom copiado:', cupom);
                alert('Cupom copiado! ✅');
            })
            .catch(err => {
                console.error('Erro ao copiar:', err);
            });
        }
    }
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
  padding: 0 0 200px 0;
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

  
</style>

