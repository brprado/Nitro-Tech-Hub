<template>
  <div id="app">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <div class="title-container">
            <h1>
              <span class="letter">N</span>
              <span class="letter">I</span>
              <span class="letter">T</span>
              <span class="letter">R</span>
              <span class="letter">O</span>
              <span class="space"></span>
              <span class="letter">T</span>
              <span class="letter">E</span>
              <span class="letter">C</span>
              <span class="letter">H</span>
              <span class="space"></span>
              <span class="letter">H</span>
              <span class="letter">U</span>
              <span class="letter">B</span>
            </h1>
            <div class="rocket-animation">
              <div class="rocket" @click="launchRocket" :class="{ 'rocket-launched': isRocketLaunched }">🚀</div>
            </div>
          </div>
          <p ref="descriptionText">{{ displayedText }}<span class="cursor" v-if="isTyping">|</span></p>
        </div>
      </div>
    </section>

    <!-- Solutions Section -->
    <section class="solutions-section">
      <div class="container">
        <div class="solutions-grid">
          <!-- NitroFund -->
          <div class="solution-card">
            <div class="solution-header">
              <img src="/nitrofundlogo2.png" alt="NitroFund Logo" class="solution-logo">
              <div class="solution-title">
                <span class="status-badge status-live">Em Produção</span>
                <h3>NitroFund</h3>
              </div>
            </div>
            <p>
              Sistema de gerenciamento de reembolsos para análise de fluxo de chargebacks e pedidos de reembolso. 
              Nossa plataforma possui gráficos intuitivos e dashboards avançados para você tomar as melhores 
              decisões financeiras com base em dados precisos e análises detalhadas.
            </p>
            <a href="https://nitrofund.com.br" target="_blank" class="btn btn-primary">
              Acessar NitroFund
            </a>
          </div>

          <!-- NitroCampaign -->
          <div class="solution-card">
            <div class="solution-header">
              <img src="/logo-nitrocampaign.png" alt="NitroCampaign Logo" class="solution-logo">
              <div class="solution-title">
                <span class="status-badge status-live">Em Produção</span>
                <h3>NitroCampaign</h3>
              </div>
            </div>
            <p>
              Software especializado em gestão de nomes e padronização de campanhas. 
              Organize seus leads, padronize processos de marketing e maximize 
              a eficiência das suas campanhas digitais.
            </p>
            <a href="https://www.nitrocampaign.com" target="_blank" class="btn btn-primary">
              Acessar NitroCampaign
            </a>
          </div>

          <!-- NitroADS -->
          <div class="solution-card">
            <div class="solution-header">
              <div class="solution-logo" style="background: linear-gradient(135deg, var(--primary-color), var(--primary-light)); color: white; font-size: 1.5rem; display: flex; align-items: center; justify-content: center;">
                📈
              </div>
              <div class="solution-title">
                <span class="status-badge status-development">Em Desenvolvimento</span>
                <h3>NitroADS</h3>
              </div>
            </div>
            <p>
              BI operacional avançado para gestão de anúncios em plataformas digitais. 
              Monitore performance, otimize investimentos e tome decisões baseadas 
              em dados reais para maximizar o ROI das suas campanhas.
            </p>
            <button class="btn btn-secondary" disabled>
              Em Breve
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <p>&copy; 2025 NitroCompany. Todos os direitos reservados.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isRocketLaunched: false,
      displayedText: '',
      fullText: 'Hub de soluções tecnológicas para otimizar seu dia-dia aqui na Nitro!',
      isTyping: true,
      typeSpeed: 80
    }
  },
  mounted() {
    this.startTyping();
  },
  methods: {
    launchRocket() {
      if (this.isRocketLaunched) return; // Previne múltiplos cliques
      
      this.isRocketLaunched = true;
      
      // Reset após 3 segundos
      setTimeout(() => {
        this.isRocketLaunched = false;
      }, 3000);
    },
    startTyping() {
      let i = 0;
      const timer = setInterval(() => {
        if (i < this.fullText.length) {
          this.displayedText += this.fullText.charAt(i);
          i++;
        } else {
          clearInterval(timer);
          this.isTyping = false;
        }
      }, this.typeSpeed);
    }
  }
}
</script>
