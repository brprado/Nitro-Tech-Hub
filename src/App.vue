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
      
      <!-- Clouds Container -->
      <div class="clouds" v-if="!isDarkMode">
        <div 
          v-for="(cloud, index) in clouds" 
          :key="index"
          class="cloud"
          :style="cloud.style"
        >
          <div class="cloud-shape"></div>
        </div>
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
                <span class="status-badge status-live">EM PRODUÇÃO</span>
                <h3>NitroADS</h3>
              </div>
            </div>
            <p>
              BI operacional avançado para gestão de anúncios em plataformas digitais. 
              Monitore performance, otimize investimentos e tome decisões baseadas 
              em dados reais para maximizar o ROI das suas campanhas.
            </p>
            
            <!-- Tutorial Video Section -->
            <div class="tutorial-section">
              <h4>📚 Tutoriais de Acesso</h4>
              
              <!-- Desktop Tutorial Video -->
              <div class="video-container">
                <h5>🖥️ Como acessar pelo Desktop/Web:</h5>
                <iframe 
                  width="100%" 
                  height="200" 
                  src="https://kommodo.ai/recordings/bl7ti91xOM8HiwPhQcjj" 
                  title="Tutorial Completo do Dashboard de Tráfego Pago no Power BI" 
                  frameborder="0" 
                  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                  referrerpolicy="strict-origin-when-cross-origin" 
                  allowfullscreen>
                </iframe>
              </div>
              
              <!-- Mobile Tutorial Link -->
              <div class="mobile-tutorial">
                <h5>📱 Como acessar pelo Celular:</h5>
                <a href="https://youtube.com/shorts/3RnKtMliY5w?si=FOpvxWaKJe0SH2nP" target="_blank" class="btn btn-secondary">
                  📺 Ver Tutorial Mobile
                </a>
              </div>
            </div>
            
            <a href="https://app.powerbi.com/groups/me/apps/d21319f2-d5ca-4af6-90cd-55113058f2b6/reports/6d63b8aa-bd0e-48ac-afa3-e496540f25b2/fe947560a908e83dad98?ctid=6ce8ae7f-5944-4992-a0f3-1fe4f6b73f1b&experience=power-bi" target="_blank" class="btn btn-primary">
              Acessar NitroADS
            </a>
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
      shootingStarInterval: null,
      clouds: [],
      cloudInterval: null
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
        this.stopClouds();
      } else {
        this.stopShootingStars();
        this.startClouds();
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
      } else {
        this.startClouds();
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
    },
    createCloud() {
      const cloudCount = Math.floor(Math.random() * 2) + 1; // 1 ou 2 nuvens
      const newClouds = [];
      
      for (let i = 0; i < cloudCount; i++) {
        const delay = i * 0.5; // Delay menor entre cada nuvem
        const offsetX = Math.random() * 200 - 100; // Offset X aleatório (-100px a 100px)
        const offsetY = Math.random() * 100 - 50; // Offset Y aleatório (-50px a 50px)
        const duration = Math.random() * 2 + 3; // Duração entre 3s e 5s (mais rápido)
        const size = Math.random() * 0.5 + 0.8; // Tamanho entre 0.8 e 1.3
        
        newClouds.push({
          style: {
            right: `calc(-100px + ${offsetX}px)`,
            top: `calc(-100px + ${offsetY}px)`,
            animationDelay: delay + 's',
            animationDuration: duration + 's',
            transform: `scale(${size})`
          }
        });
      }
      
      this.clouds = [...this.clouds, ...newClouds];
      
      // Remove as nuvens após a animação
      setTimeout(() => {
        this.clouds = this.clouds.slice(cloudCount);
      }, 6000);
    },
    startClouds() {
      if (this.cloudInterval) {
        clearInterval(this.cloudInterval);
      }
      
      this.cloudInterval = setInterval(() => {
        if (!this.isDarkMode) {
          this.createCloud();
        }
      }, 2000);
    },
    stopClouds() {
      if (this.cloudInterval) {
        clearInterval(this.cloudInterval);
        this.cloudInterval = null;
      }
      this.clouds = [];
    }
  }
}
</script>
