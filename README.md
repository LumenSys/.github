# LumenSys - Projeto de Graduação

## 📋 Sobre o Projeto

Este repositório contém a organização e documentação do projeto de graduação desenvolvido pela equipe LumenSys. O projeto foca no desenvolvimento de soluções inovadoras utilizando tecnologias modernas para resolver problemas do mundo real.

## 🎯 Objetivos

### Objetivo Geral
Desenvolver uma solução tecnológica completa que demonstre a aplicação prática dos conhecimentos adquiridos durante o curso de graduação.

### Objetivos Específicos
- Implementar uma arquitetura de software escalável e eficiente
- Aplicar metodologias ágeis de desenvolvimento
- Integrar tecnologias modernas de frontend e backend
- Desenvolver uma interface de usuário intuitiva e responsiva
- Implementar testes automatizados e CI/CD
- Documentar todo o processo de desenvolvimento

## 🚀 Tecnologias Utilizadas

### Frontend
- **React.js** - Biblioteca para construção de interfaces
- **TypeScript** - Superset do JavaScript com tipagem estática
- **Tailwind CSS** - Framework CSS utilitário
- **Vite** - Build tool e servidor de desenvolvimento

### Backend
- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web para Node.js
- **PostgreSQL** - Banco de dados relacional
- **Redis** - Cache em memória
- **Docker** - Containerização

### DevOps e Ferramentas
- **GitHub Actions** - CI/CD
- **Docker Compose** - Orquestração de containers
- **Jest** - Framework de testes
- **ESLint/Prettier** - Linting e formatação de código

## 📁 Estrutura do Projeto

```
LumenSys/
├── frontend/          # Aplicação React
├── backend/           # API Node.js
├── database/          # Scripts e migrações do banco
├── docs/             # Documentação do projeto
├── tests/            # Testes automatizados
└── deployment/       # Configurações de deploy
```

## 🛠️ Instalação e Configuração

### Pré-requisitos
- Node.js (v18 ou superior)
- Docker e Docker Compose
- PostgreSQL
- Git

### Passos para Instalação

1. **Clone o repositório principal:**
   ```bash
   git clone https://github.com/LumenSys/[nome-do-projeto]
   cd [nome-do-projeto]
   ```

2. **Instale as dependências:**
   ```bash
   npm install
   ```

3. **Configure as variáveis de ambiente:**
   ```bash
   cp .env.example .env
   # Edite o arquivo .env com suas configurações
   ```

4. **Execute com Docker:**
   ```bash
   docker-compose up -d
   ```

## 📚 Metodologia

### Metodologia de Desenvolvimento
- **Scrum** - Framework ágil para gestão do projeto
- **Git Flow** - Estratégia de branching
- **Test Driven Development (TDD)** - Desenvolvimento orientado a testes
- **Code Review** - Revisão de código em todas as mudanças

### Cronograma do Projeto
- **Fase 1** - Planejamento e Análise de Requisitos (2 semanas)
- **Fase 2** - Design e Arquitetura do Sistema (2 semanas)
- **Fase 3** - Desenvolvimento do MVP (6 semanas)
- **Fase 4** - Testes e Refinamentos (3 semanas)
- **Fase 5** - Documentação e Apresentação (1 semana)

## 👥 Equipe

| Nome | Função | GitHub |
|------|--------|--------|
| [ Franciane Ramos Franco ] | Scrum Master / Full Stack | [ @FrancianeRamos ] |
| [ Rodrigo Yoshida Lombezzi ] | Scrum Master / Full Stack | [ @rodrigo-lombezzi ] |


## 📖 Documentação

- [Documentação da API](./docs/api.md)
- [Guia de Contribuição](./docs/contributing.md)
- [Arquitetura do Sistema](./docs/architecture.md)
- [Manual do Usuário](./docs/user-manual.md)

## 🧪 Testes

### Executar Testes
```bash
# Testes unitários
npm run test

# Testes de integração
npm run test:integration

# Cobertura de testes
npm run test:coverage
```

### Estratégia de Testes
- **Testes Unitários** - Jest para componentes e funções
- **Testes de Integração** - Cypress para fluxos completos
- **Testes de API** - Supertest para endpoints
- **Testes de Performance** - Artillery para carga

## 📊 Resultados e Métricas

### Métricas de Qualidade
- Cobertura de testes: >80%
- Performance Score: >90%
- Accessibility Score: >95%
- SEO Score: >90%

### Benchmarks de Performance
- Tempo de carregamento inicial: <2s
- Time to Interactive: <3s
- Throughput da API: >1000 req/s

## 🚀 Deploy e Produção

O projeto está configurado para deploy automático através do GitHub Actions:

- **Desenvolvimento**: Deploy automático na branch `develop`
- **Staging**: Deploy automático na branch `staging`
- **Produção**: Deploy manual via tags de release

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 📞 Contato

- **Email**: [email@lumensys.com]
- **LinkedIn**: [LumenSys Team]
- **Website**: [https://lumensys.com]

## 🙏 Agradecimentos

- Orientador: [Jefferson Ribeiro  Antônio Passerini]
- Instituição: [Fatec Jales - Profº José Camargo]

---

**Desenvolvido com ❤️ pela equipe LumenSys**
