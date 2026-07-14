<template>
  <div id="container-consultancy">  

    <div id="banner">
      
    </div>

    <div id="problem">
      <h1>O Problema</h1>
      <h2>"O ambiente está funcional, mas não parece meu. Falta alguma coisa eu não sei o quê"</h2>
      <p>
        Se <strong>você já se sentiu assim</strong>, provavelmente <strong>não</strong> precisa de uma reforma. 
        Precisa de direção: uma paleta de cores que faça sentido, uma <strong>organização de layout</strong> que melhore a circulação
         e <strong> peças certas</strong> nos lugares certos.
         É exatamente isso que o <strong> Olhar Ilia entrega.</strong>
      </p>

    </div>

    <div id="included">

      <h3>O que está incluso</h3>

      <div id="cards">

        <div id="card">
          <img src="">
          <h4>Organização de Layout</h4>
          <p>
            Um <strong>desenho esquemático</strong> mostrando como reorganizar o que você já tem. <strong>Sem reforma</strong>, sem compra obrigatória.
          </p>
        </div>

        <div id="card">
          <img src="">
          <h4>Paleta de cores</h4>
          <p>
            Sugestão de <strong>tinta</strong> com referência de <strong>cor</strong> (marca e código) e como ela <strong>conversa</strong> com o que <Strong>já existe</Strong>.
          </p>
        </div>


        <div id="card">
          <img src="">
          <h4>Curadoria de peças</h4>
          <p>
            Seleção de <strong>decorativos, têxteis</strong> e <strong>iluminação</strong> com <strong>indicação</strong> de onde <strong>comprar</strong>.
          </p>

        </div>


        <div id="card">
          <img src="">
          <h4>Lista de compras</h4>
          <p>
            Tabela com <strong>item, loja</strong> e <strong>faixa de preço</strong>. Tudo pronto pra <strong>você executar</strong> no <strong>seu ritmo</strong>.
          </p>
        </div>

      </div>

        


        <p>
          Tudo entregue em PDF via e-mail, em até 7 dias úteis após o preenchimento do briefing.
        </p>

    </div>

    <div id="not-included">
       <h3>
        O que não está incluso
       </h3>

       <p>
        Plantas técnicas, projeto hidráulico ou elétrico,
         acompanhamento de obra e orçamento com fornecedores.
       </p>
    </div>

    <div id="how-it-works">
      <h3>Como funciona</h3>

      <div id="text-1">
        <span>01</span>
        <p>
          Você faz o pagamento e recebe um formulário de briefing. Perguntas sobre o ambiente, 
          o que incomoda, referências que você gosta e fotos com medidas básicas.
        </p>
      </div>

      <div id="text-2">
        <span>02</span>
        <p>
          Eu trabalho com o que você enviou. Sem reuniões longas, sem idas e vindas.
           Escopo fechado, entrega focada.
        </p>
      </div>
       
      <div id="text-3">
        <span>03</span>
        <p>
          Você recebe o PDF em até 7 dias úteis. Com uma rodada de ajuste incluída caso algo não faça sentido pro seu contexto.
        </p>
      </div>
    </div>

    <div id="investment">
      <h3>Investimento</h3>
      <div id="investment-info">        

        <div>
          <span>Ambiente único</span>
          <span>R$ 500</span>
        </div>
        <div>
          <span>Dois ambientes integrados</span>
          <span>R$ 800 a R$ 1.200</span>
        </div>
        <p>
          O valor da consultoria não inclui as peças e materiais da lista de compras. 
          Esses são custos separados que você decide se e quando executar.
        </p>

      </div>
    </div>

    <div id="this-is-not-for-you-if">

      <h3>
        Isso não é pra você se...
      </h3>

      <p>
        Você precisa de projeto executivo, acompanhamento de obra ou quer reformar estruturalmente o espaço.
         Para esses casos, o caminho é o projeto completo e a gente pode conversar sobre isso também.
      </p>
      
      <span>
        Pronta pra dar direção pro seu espaço?
      </span>

      <a :href="whatsappLink()" target="_blank">Sim, quero uma consultoria!</a>

    </div>
    <Contacts /> 
    <Footer />      
  </div>
</template> 


<script>
import App from '@/App.vue';
import Contacts from '@/components/Contacts.vue';
import Footer from '@/components/Footer.vue';
export default {
  name: 'ConsultancyView',
  inject: ['whatsappLink'],    
  components: {
    Contacts,
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

h1, h3 {
  text-transform: uppercase;
}

#banner {
  width: 100%;
  height: 70vh;
  background-image: url('../assets/desktop-consultancy.webp');
  background-repeat: no-repeat;
  background-size: cover;
}

#problem {
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#problem h1,
#problem h2,
#problem p,
#problem strong {
  color: var(--color-8);
  margin: 30px 0 0 0;
  width: 70%;
  text-wrap: balance;
  animation: colorTransition 2s ease-in;
  animation-delay: 0s;
  animation-fill-mode: forwards;
  text-align: center;
}

#problem h2 {
  font-style: italic;
}

#included {
  height: auto;
  padding: 80px 0;
  background-color: var(--color-9);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#included h3,
#included p {
  color: var(--color-7);
  text-align: center;
  text-wrap: balance;
}

#included h3,
#included h4 {
  font-weight: bold;
}

#cards {
  margin: 50px 0;
  display: grid;
  grid-template-columns: auto auto;
  justify-content: center;
  align-items: center;
  gap: 20px;
  text-align: center;
}

#card {
  background-color: var(--color-7);
  text-align: center;
  color: var(--color-9);
  width: 300px;
  height: 300px;
  border-radius: 8px;
  padding: 10px;
}

#card p,
#card h4,
#card strong {
  color: var(--color-9);
}

#card p {
  margin: 20px 0 0 0;
  text-align: start; 
}

 @keyframes colorTransition {

    0% {
      color: var(--color-8); 
    }

    100% {
      color: var(--color-9);  
    }
}

#not-included {
  padding: 100px 20px;
  text-align: center;
}

#not-included h3,
#not-included p {
  color: var(--color-9); 
  text-wrap: balance; 
}

#not-included h3 {
  font-weight: bold;
}

#not-included p {
  margin: 50px 0 0 0;
}

#how-it-works {
  background-color: var(--color-9);
  padding: 100px 20px;
}

#how-it-works h3 {
  text-align: center;
  margin: 0 0 50px 0;
  font-weight: bold;
}

#text-1,
#text-2,
#text-3 {
  margin: auto;
  width: 60%;
  display: flex;
  flex-direction: column;
}

#text-1 span,
#text-2 span,
#text-3 span {
  font-weight: bold;
  font-size: 1.5rem;
}

#how-it-works h3,
#how-it-works p,
#how-it-works span {
  color: var(--color-7);
}

#investment {
  background-color: var(--color-7);
  padding: 100px 0;
  text-align: center;
}

#investment h3 {
  font-weight: bold;
  color: var(--color-9);
  margin: 0 0 100px 0;
}

#investment-info {
  background-color: var(--color-9);
  width: 60%;
  border-radius: 10px;
  margin: auto;
  padding: 50px 50px;
  text-align: start;
}

#investment-info div {
  margin: 10px 0 0 0;
}

#investment-info h3,
#investment-info span,
#investment-info p {
  color: var(--color-7);
}

#investment-info div {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

#investment-info p {
  margin: 20px 0 0 0;
}

#this-is-not-for-you-if {
  background-color: var(--color-9);
  text-align: center;
  padding: 100px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

#this-is-not-for-you-if h3 {
  font-weight: bold;
}

#this-is-not-for-you-if p {
  text-align: start;
  margin: 20px 0 50px 0;
}

#this-is-not-for-you-if h3,
#this-is-not-for-you-if p,
#this-is-not-for-you-if span {
  color: var(--color-7);
  width: 60%;
}

#this-is-not-for-you-if span {
  font-weight: bold;
}

#this-is-not-for-you-if a {
  margin: 35px 0 0 0;
  padding: 10px;
  background-color: var(--color-7);
  color: var(--color-9);
  text-decoration: none;
  font-weight: bold;
  border-radius: 4px;
}


@media (max-width: 992px) {

  #banner {
    background-image: url('../assets/mobile-consultancy.webp');
  }

  #problem {
    padding: 50px 0;
  }

  #problem h1,
  #problem h2,
  #problem p,
  #problem strong {
    width: 90%;
  }

  #problem h1 {
    font-size: 1.6rem;
  }

  #problem h2 {
    font-size: 1.4rem;
  }

  #problem p {
    font-size: 1.2rem;
  }

  #text-1,
  #text-2,
  #text-3 {
    width: 90%;
    text-wrap: balance;
  }
  
  #investment-info {
    width: 90%;
    padding: 50px 20px;
  }
  

  #investment-info div {
    display: flex;
    flex-direction: column;
  }

  #this-is-not-for-you-if h3,
  #this-is-not-for-you-if p,
  #this-is-not-for-you-if span {
    width: 90%;
  }
}


@media (max-width: 720px) {

#cards {
  display: grid;
  grid-template-columns: auto auto;
  justify-content: center;
  align-items: center;
  gap: 20px;
}

#card {  
  width: 220px;
  height: 280px;
}

}

@media (max-width: 540px) {
  #problem p {
    text-align: start;
    width: 90%;
  }

  #cards {
    display: grid;
    grid-template-columns: auto;
    justify-content: center;
    align-items: center;
    gap: 20px 0;
  }

  #card {  
    width: 250px;
    height: 250px;
  }

}



</style>

