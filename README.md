# Nitro Tech Hub

Hub das soluções tecnológicas da Nitro Tech Hub, apresentando os softwares desenvolvidos pela empresa.

## 🚀 Softwares Disponíveis

### NitroFund
- **Status**: Em Produção
- **Descrição**: Sistema de gerenciamento de reembolsos empresariais
- **URL**: https://nitrofund.com.br

### NitroCampaign
- **Status**: Em Produção  
- **Descrição**: Software de gestão de nomes e padronização de campanhas
- **URL**: https://www.nitrocampaign.com

### NitroADS
- **Status**: Em Desenvolvimento
- **Descrição**: BI operacional para gestão de anúncios em plataformas digitais

## 🛠️ Tecnologias Utilizadas

- **Frontend**: Vue.js 3
- **Build Tool**: Vite
- **Styling**: CSS3 com design responsivo
- **Deploy**: Docker + Nginx
- **Plataforma**: Railway

## 📦 Instalação e Desenvolvimento

### Pré-requisitos
- Node.js 18+
- npm ou yarn

### Instalação
```bash
# Instalar dependências
npm install

# Executar em modo desenvolvimento
npm run dev

# Build para produção
npm run build
```

## 🐳 Deploy com Docker

### Build da imagem
```bash
docker build -t nitro-tech-hub .
```

### Executar container
```bash
docker run -p 80:80 nitro-tech-hub
```

## 🚂 Deploy no Railway

1. Conecte seu repositório GitHub ao Railway
2. O Railway detectará automaticamente o Dockerfile
3. O deploy será feito automaticamente a cada push na branch principal

### Configurações do Railway
- **Builder**: Dockerfile
- **Port**: 80 (automático)
- **Health Check**: `/health`

## 📱 Responsividade

A aplicação é totalmente responsiva e funciona perfeitamente em:
- Desktop
- Tablet
- Mobile

## 🎨 Design

- Interface moderna e profissional
- Gradientes e sombras para profundidade
- Animações suaves de hover
- Tipografia Inter para melhor legibilidade
- Cores da marca Nitro Tech Hub

## 📄 Estrutura do Projeto

```
nitro-tech-hub/
├── src/
│   ├── App.vue          # Componente principal
│   ├── main.js          # Ponto de entrada
│   └── style.css        # Estilos globais
├── Dockerfile           # Configuração Docker
├── nginx.conf           # Configuração Nginx
├── railway.json         # Configuração Railway
├── package.json         # Dependências
├── vite.config.js       # Configuração Vite
└── index.html           # Template HTML
```

## 🔧 Comandos Úteis

```bash
# Desenvolvimento
npm run dev

# Build
npm run build

# Preview do build
npm run preview

# Docker build
docker build -t nitro-tech-hub .

# Docker run
docker run -p 80:80 nitro-tech-hub
```

## 📞 Suporte

Para dúvidas ou suporte, entre em contato com a equipe da NitroCompany.
