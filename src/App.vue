<template>
  <div id="app">
    <!-- Hero Section -->
    <section class="hero">
      <!-- Shooting Stars Container -->
      <div class="shooting-stars" v-if="isDarkMode">
        <div 
          v-for="(star, index) in shootingStars" 
          :key="index"
          class="shooting-star"
          :style="star.style"
        ></div>
      </div>
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
              <span class="letter">H</span>
              <span class="letter">U</span>
              <span class="letter">B</span>
            </h1>
            <div class="header-controls">
              <div class="theme-toggle" @click="toggleTheme" :class="{ 'dark-mode': isDarkMode }">
                <span class="theme-icon">{{ isDarkMode ? '🌙' : '☀️' }}</span>
              </div>
              <div class="rocket-animation">
                <div class="rocket" @click="launchRocket" :class="{ 'rocket-launched': isRocketLaunched }">🚀</div>
              </div>
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

          <!-- Niko -->
          <div class="solution-card">
            <div class="solution-header">
              <div class="solution-logo" style="background: linear-gradient(135deg, var(--primary-color), var(--primary-light)); color: white; font-size: 1.5rem; display: flex; align-items: center; justify-content: center;">
                🤖
              </div>
              <div class="solution-title">
                <span class="status-badge status-live">Em Produção</span>
                <h3>Niko<span class="neon-star">✦</span></h3>
              </div>
            </div>
            <p>
              Atendente de IA inteligente para suporte ao cliente. Abre tickets automaticamente, 
              processa reembolsos no <span class="highlight-nitrofund">NitroFund</span>, tira dúvidas de clientes e realiza vendas de forma autônoma. 
              Tecnologia de ponta para otimizar o atendimento 24/7.
            </p>
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
              <img src="/bi-image.png" alt="NitroADS BI Logo" class="solution-logo">
              <div class="solution-title">
                <span class="status-badge status-development">
                  Em Desenvolvimento
                  <span class="hammer-animation">🔨</span>
                </span>
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
      typeSpeed: 80,
      isDarkMode: false,
      shootingStars: [],
      shootingStarInterval: null
    }
  },
  mounted() {
    this.startTyping();
    this.loadTheme();
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
    },
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode;
      this.applyTheme();
      this.saveTheme();
      
      if (this.isDarkMode) {
        this.startShootingStars();
      } else {
        this.stopShootingStars();
      }
    },
    applyTheme() {
      const root = document.documentElement;
      if (this.isDarkMode) {
        root.classList.add('dark-theme');
        root.classList.remove('light-theme');
      } else {
        root.classList.add('light-theme');
        root.classList.remove('dark-theme');
      }
    },
    saveTheme() {
      localStorage.setItem('theme', this.isDarkMode ? 'dark' : 'light');
    },
    loadTheme() {
      const savedTheme = localStorage.getItem('theme');
      if (savedTheme === 'dark') {
        this.isDarkMode = true;
      } else {
        this.isDarkMode = false;
      }
      this.applyTheme();
      
      if (this.isDarkMode) {
        this.startShootingStars();
      }
    },
    createShootingStar() {
      const starCount = Math.floor(Math.random() * 2) + 2; // 2 ou 3 estrelas
      const newStars = [];
      
      for (let i = 0; i < starCount; i++) {
        const delay = i * 0.5; // Delay entre cada estrela
        const startX = Math.random() * 100; // Posição X aleatória
        const startY = Math.random() * 50; // Posição Y aleatória
        const duration = Math.random() * 2 + 1.5; // Duração entre 1.5s e 3.5s
        
        newStars.push({
          style: {
            left: startX + '%',
            top: startY + '%',
            animationDelay: delay + 's',
            animationDuration: duration + 's'
          }
        });
      }
      
      this.shootingStars = [...this.shootingStars, ...newStars];
      
      // Remove as estrelas após a animação
      setTimeout(() => {
        this.shootingStars = this.shootingStars.slice(starCount);
      }, 4000);
    },
    startShootingStars() {
      if (this.shootingStarInterval) {
        clearInterval(this.shootingStarInterval);
      }
      
      this.shootingStarInterval = setInterval(() => {
        if (this.isDarkMode) {
          this.createShootingStar();
        }
      }, 3000);
    },
    stopShootingStars() {
      if (this.shootingStarInterval) {
        clearInterval(this.shootingStarInterval);
        this.shootingStarInterval = null;
      }
      this.shootingStars = [];
    }
  }
}
</script>
