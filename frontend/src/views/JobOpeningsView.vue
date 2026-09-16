<template>

    <div class="content">    
        <div class="job-card">

        <img
            src="@/assets/banheiro/capa.webp"
            alt="Projeto de arquitetura"
            class="job-image"
        >

        <div class="job-content">

            <span class="job-type">
                Estágio
            </span> 

            <h2>Estágio em Arquitetura</h2>

            <div class="job-info">
                <span>Remoto</span>
                <span>Meio período</span>
            </div>

            <p class="job-description">
                Venha fazer parte da nossa equipe como estagiário! 
            </p>

            <h3>Requisitos</h3>

            <ul class="requirements">
                <li>Estar cursando Arquitetura e Urbanismo</li>
                <li>Conhecimento em SketchUp</li>
                <li>Conhecimento em V-Ray</li>
                <li>Conhecimento em AutoCAD</li>
                <li>Noções de desenvolvimento e renderização de projetos de interiores</li>  
            </ul>

            <a href="https://forms.gle/ekrQb1ExA6VjhZAK6" @click="redirectToLink" target="_blank">
                <button class="apply-button">
                    Inscreva-se
                </button> 
            </a>


        </div>

    </div>
   

    </div>
     <Footer />
   
</template>

<script>
import Footer from '@/components/Footer.vue';

export default {
  name: 'Jobs',
  components: {     
    Footer,  
  },

  methods: {
    redirectToLink() {
        
        setTimeout(() => {
            window.location.href = 'https://www.iliaarquitetura.com.br/';
        }, 3000)
    }
  }  

}


</script>


<style scoped>

.content {
    padding: 300px 50px 100px 50px;
    display: flex;
    justify-content: start;
    align-items: center;
    flex-direction: row;
}

.job-card {
    width: 380px;
    background: var(--color-7);
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--color-2);
    box-shadow: 0 4px 15px rgba(79, 73, 63, 0.12);

}

@media (max-width: 700px) {

    .content {
      padding: 200px 0 50px 0;
      display: flex;
      justify-content: center;  
    }

    .job-card {
        width: 90%;
    }
}

.job-image {
    width: 100%;
    height: 180px;
    object-fit: cover;
}

.job-content {
    padding: 24px;
}

.job-type {
    display: inline-block;
    margin-bottom: 10px;
    padding: 5px 10px;
    border-radius: 6px;
    background: var(--color-5);
    color: var(--color-1);
    font-size: 13px;
    font-weight: 600;
}

h2 {
    margin: 0 0 12px;
    color: var(--color-8);
    font-size: 22px;
    line-height: 1.3;
}

.job-info {
    display: flex;
    gap: 8px;
    margin-bottom: 15px;
}

.job-info span {
    padding: 5px 10px;
    border-radius: 6px;
    background: var(--color-2);
    color: var(--color-4);
    font-size: 13px;
}

.job-description {
    color: var(--color-4);
    font-size: 14px;
    line-height: 1.5;
}

h3 {
    margin-top: 20px;
    margin-bottom: 10px;
    color: var(--color-8);
    font-size: 16px;
}

.requirements {
    padding-left: 20px;
    margin-bottom: 24px;
}

.requirements li {
    margin-bottom: 7px;
    color: var(--color-4);
    font-size: 14px;
}

.apply-button {
    width: 100%;
    padding: 12px;
    border: none;
    border-radius: 7px;
    background: var(--color-1);
    color: var(--color-7);
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    
}

.apply-button:hover {
    background: var(--color-3);
    transition: 1s;
}

.apply-button:active {
    transform: scale(0.98);
}

</style>

