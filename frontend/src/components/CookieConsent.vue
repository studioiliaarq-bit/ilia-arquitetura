
<template>
  <div v-if="!accepted" class="privacy-overlay">

    <div class="cookie-banner">

      <div class="privacy-content">

        <h2>Privacidade e proteção de dados</h2>

        <p>
          Este site utiliza cookies necessários para seu funcionamento e poderá
          utilizar cookies opcionais para melhorar sua experiência de navegação.
        </p>

        <p>
          Em conformidade com a
          <strong>Lei Geral de Proteção de Dados Pessoais (LGPD)</strong> —
          Lei nº 13.709/2018 —, o tratamento de dados pessoais será realizado
          de acordo com as finalidades informadas e com as medidas adequadas
          de segurança e proteção.
        </p>

        <p>
          Você pode aceitar ou recusar os cookies opcionais. A recusa não
          impedirá sua navegação pelo site, mas algumas funcionalidades
          adicionais poderão não estar disponíveis.
        </p>

        <p>
          Para saber mais sobre como seus dados são tratados, consulte nossa
          <router-link to="">
            Política de Privacidade
          </router-link>
        </p>

      </div>

      <div class="actions">

        <button
          class="btn-accept"
          @click="acceptCookies"
        >
          Aceitar
        </button>

        <button
          class="btn-reject"
          @click="rejectCookies"
        >
          Recusar
        </button>

      </div>

    </div>

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const accepted = ref(true);

onMounted(() => {
  const consent = localStorage.getItem('cookie_consent');

  if (!consent) {
    accepted.value = false;
  }
});

function acceptCookies() {
  localStorage.setItem('cookie_consent', 'accepted');

  accepted.value = true;
}

function rejectCookies() {
  localStorage.setItem('cookie_consent', 'rejected');

  // Permite continuar navegando normalmente
  accepted.value = true;
}
</script>

<style scoped>

.privacy-overlay {
  position: fixed;
  inset: 0;
  background-color: transparent;
  

  display: flex;
  justify-content: center;
  align-items: flex-end;

  z-index: 9999;
}

.cookie-banner {
  width: 100%;
  background-color: var(--color-1);
  color: var(--color-7);

  padding: 25px 30px;

  box-sizing: border-box;

  box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.25);
}

.privacy-content {
  max-width: 1100px;
  margin: 0 auto;
}

.privacy-content h2 {
  margin: 0 0 15px;
  font-size: 20px;
}

.privacy-content p {
  margin: 8px 0;

  font-size: 14px;
  line-height: 1.6;
}

.privacy-content a {
  color: var(--color-6);
  text-decoration: underline;
}

.actions {
  max-width: 1100px;

  margin: 20px auto 0;

  display: flex;
  justify-content: flex-end;
  gap: 10px;
}

.actions button {
  padding: 10px 20px;

  border: none;
  border-radius: 5px;

  cursor: pointer;

  font-size: 14px;
  font-weight: 600;
}

.btn-accept {
  background-color: var(--color-4);
  color: var(--color-7);
}

.btn-accept:hover, .btn-reject:hover {
  background-color: var(--color-3);
}

.btn-reject {
  background-color: var(--color-4);
  color: var(--color-7);
}



@media (max-width: 768px) {

  .cookie-banner {
    padding: 20px;
  }

  .actions {
    flex-direction: column;
  }

  .actions button {
    width: 100%;
  }

}

</style>

