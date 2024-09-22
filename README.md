# Frontend - Detecção de Fraude em Transações com Machine Learning

## Descrição do Projeto

Este é o frontend da aplicação de **detecção de fraudes** em transações de cartão de crédito. Ele permite que os usuários enviem informações de novas transações e escolham entre diferentes modelos de machine learning (KNN, Árvore de Decisão, Naive Bayes) para prever se uma transação é fraudulenta ou não.

A interface foi construída utilizando **React** com **TypeScript** e **Vite** como bundler, além de **Tailwind CSS** para estilização. O frontend consome a API desenvolvida no back-end do projeto para fazer predições baseadas nos dados fornecidos pelo usuário.

## Estrutura do Repositório

```bash
.
├── eslint.config.js                # Configuração do ESLint para o projeto
├── index.html                      # Página HTML principal
├── package-lock.json               # Arquivo de controle de dependências
├── package.json                    # Lista de dependências e scripts do projeto
├── postcss.config.js               # Configuração do PostCSS para o Tailwind
├── public                          # Arquivos públicos estáticos
│   └── vite.svg
├── src                             # Código-fonte do frontend
│   ├── App.tsx                     # Componente principal da aplicação React
│   ├── assets                      # Diretório para armazenar ativos (imagens, ícones, etc.)
│   ├── index.css                   # Estilos globais da aplicação
│   ├── main.tsx                    # Ponto de entrada do React
│   └── vite-env.d.ts               # Definições de ambiente para o Vite e TypeScript
├── tailwind.config.js              # Configuração do Tailwind CSS
├── tsconfig.app.json               # Configurações do TypeScript para o projeto
├── tsconfig.json                   # Configurações gerais do TypeScript
├── tsconfig.node.json              # Configuração específica para Node.js
└── vite.config.ts                  # Configuração do Vite para o build do projeto
```

## Funcionalidades

- **Formulário de entrada de dados:** Permite que os usuários insiram dados de uma transação (latitude, longitude, valor e tempo decorrido).
- **Escolha do modelo:** O usuário pode escolher entre três diferentes algoritmos de machine learning: KNN, Árvore de Decisão ou Naive Bayes.
- **Predição em tempo real:** O sistema faz a predição e retorna se a transação é fraudulenta ou não.

## Pré-requisitos

- **Node.js** (versão 14 ou superior) e **npm** (ou **yarn**) instalados na sua máquina.

## Como Executar o Projeto

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/pedro-git-projects/mvp-puc-credit-card-fraud-prediction-frontend
   cd mvp-puc-credit-card-fraud-prediction-frontend
   ```

2. **Instale as dependências:**

   ```bash
   npm install
   ```

   ou

   ```bash
   yarn install
   ```

3. **Configure o Back-End:**
   
   O frontend precisa que o back-end da aplicação esteja rodando para consumir os endpoints. Certifique-se de que a aplicação FastAPI está disponível e rodando na URL `http://localhost:8000`.

4. **Execute o projeto:**

   Inicie o servidor de desenvolvimento com:

   ```bash
   npm run dev
   ```

   ou

   ```bash
   yarn dev
   ```

5. **Acesse a aplicação no navegador:**

   Após executar o comando acima, abra o navegador e acesse `http://localhost:5173/` para ver a aplicação.

## Estrutura dos Dados de Entrada

O formulário da aplicação coleta os seguintes dados da transação para análise:

- **Time Elapsed (`time_elapsed`)**: Tempo decorrido desde a última transação (em segundos).
- **Transaction Amount (`amt`)**: Valor da transação.
- **Latitude (`lat`)**: Latitude do local da transação.
- **Longitude (`long`)**: Longitude do local da transação.

Esses dados são enviados para o backend para realizar a predição de fraude.

## Modelos de Machine Learning Disponíveis

A interface permite que o usuário selecione qual modelo de machine learning será utilizado para a predição:

- **KNN (K-Nearest Neighbors)**
- **Árvore de Decisão (Decision Tree)**
- **Naive Bayes**

Dependendo do modelo selecionado, a requisição é enviada para diferentes endpoints da API.

## Estilização

O projeto utiliza **Tailwind CSS** para estilização, que permite um desenvolvimento rápido e eficiente de interfaces modernas e responsivas. Caso deseje personalizar os estilos, as configurações estão no arquivo `tailwind.config.js`.

## Scripts Disponíveis

No `package.json`, os seguintes scripts estão disponíveis:

- **`npm run dev`**: Inicia o servidor de desenvolvimento.
- **`npm run build`**: Cria uma versão otimizada para produção.
- **`npm run preview`**: Pré-visualiza o build de produção.
- **`npm run lint`**: Executa o ESLint para verificação de erros de código.

## Considerações Finais

Este frontend faz parte de um projeto maior, onde é combinado com um back-end que realiza a detecção de fraudes. A integração foi feita de maneira modular, permitindo que novos modelos de machine learning possam ser facilmente integrados à interface, bastando adicionar novas opções de seleção e endpoints no back-end.

Para maiores informações sobre o funcionamento do modelo e do backend, veja o README no repositório correspondente ao backend.
