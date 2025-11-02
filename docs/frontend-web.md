# Front-end Web

**TeraBuum – Plataforma de E-commerce**

Projeto de interface web para uma plataforma de e-commerce voltada para venda de produtos de informática, como kits de hardware, periféricos e acessórios. O objetivo é fornecer uma experiência de compra moderna, intuitiva e responsiva, permitindo que o usuário visualize produtos, adicione itens ao carrinho, escolha métodos de pagamento e finalize pedidos de forma segura.

---

## Projeto da Interface Web

A interface foi desenvolvida em **React**, com foco em **usabilidade e design responsivo**.

### Principais características

- **Layout baseado em grid:** páginas com áreas principais para conteúdo, resumo do pedido e sidebar flutuante para informações importantes.
- **Interações do usuário:** modal de alteração de endereço, dropdown para escolha de métodos de pagamento, seleção de parcelas para cartões e alertas de confirmação de ações.
- **Páginas principais:** Home, Produtos, Carrinho, Pagamento, Pedidos, Detalhes do Pedido, Login, Registro e Admin de Estoque.
- **Componentes reutilizáveis:** Navbar, Footer, ProductCard, Loader.

---

### Wireframes

[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

---

### Design Visual

#### Paleta de cores
- **Primary:** `#24DBC5` – botões de ação, destaques e links importantes.
- **Secondary:** `#E8EEF5` – backgrounds de cards, seções e elementos secundários.
- **Black:** `#000000` – textos principais e ícones.

#### Tipografia
- **Fonte principal:** Prompt, sans-serif.
- Títulos, textos e botões seguem consistência de fonte para manter identidade visual.

#### Estilo dos componentes
- **Botões:** bordas arredondadas, cores primárias e efeito hover (`hover:bg-[#1bb3a3]`).
- **Cards e seções:** fundo secundário (`#E8EEF5`) ou branco (`#ffffff`) com sombra (`shadow`) e cantos arredondados (`rounded-lg`).
- **Inputs e selects:** bordas arredondadas, padding interno (`p-2` ou `p-3`) e cores neutras de fundo.
- **Modal de endereço:** fundo branco, cantos arredondados, sombra e sobreposição semi-transparente (`bg-black bg-opacity-50`).
- **Componentes reutilizáveis:** Navbar, Footer, cards de produto, sidebar flutuante para resumo de pedido, botões e modais.
- **Consistência visual:** todas as páginas mantêm padrão de header (Navbar), footer, cores e tipografia, garantindo experiência unificada para o usuário.

---

## Fluxo de Dados

[Diagrama ou descrição do fluxo de dados na aplicação.]

---

## Tecnologias Utilizadas

- React.js com TypeScript
- Tailwind CSS para estilização
- React Router para navegação entre páginas
- Serviços simulados via `CartService` e `VitrineService` (API mock)
- Git/GitHub para versionamento

---

## Considerações de Segurança

- **Autenticação e autorização:** controle de acesso para páginas de admin e ações sensíveis.
- **Proteção de dados sensíveis:** cartões de crédito mascarados e informações pessoais protegidas.
- **SSL/TLS:** todas as transações via HTTPS.
- **Validação de entrada:** inputs de formulário validados no frontend antes de enviar ao backend.

---

## Implantação

A implantação da aplicação distribuída foi planejada para garantir escalabilidade, segurança e facilidade de manutenção em ambientes de produção. Abaixo estão as etapas recomendadas para realizar o deploy do **front-end web da TeraBuum**.

### Etapas de Implantação

1. **Definição de Requisitos**  
   - **Hardware:** Servidor ou instância com no mínimo **2 vCPUs**, **2 GB de RAM** e **10 GB de armazenamento**.  
   - **Software:** Node.js (versão LTS recomendada), NPM ou Yarn, e um gerenciador de processos como **PM2** ou **Docker**.  
   - **Rede:** Certificado **SSL ativo** e acesso via **HTTPS** para todas as comunicações.

2. **Escolha da Plataforma de Hospedagem**  
   Opte por uma solução de hospedagem confiável que permita fácil escalabilidade:  
   - **Opções recomendadas:** AWS (EC2, Amplify, S3 + CloudFront), **Vercel**, **Netlify** ou **DigitalOcean**.  
   - **Critérios de escolha:** custo-benefício, suporte a **CI/CD** e integração com **GitHub**.

3. **Configuração do Ambiente**  
   - Clone o repositório do projeto:  
     ```bash
     git clone https://github.com/TeraBum/frontend-app.git
     cd frontend-app
     ```
   - Instale as dependências:  
     ```bash
     npm install
     ```
   - Crie e configure o arquivo `.env` com variáveis de ambiente (URLs de API, chaves de acesso, etc.).  
   - Compile o projeto para produção:  
     ```bash
     npm run build
     ```

4. **Deploy da Aplicação**  
   - Faça o upload dos arquivos gerados na pasta `/dist` ou `/build` para o servidor ou serviço de hospedagem.  
   - Configure o servidor web (Nginx, Apache ou outro) para servir os arquivos estáticos.  
   - Em ambientes automatizados (**CI/CD**), configure pipelines para o **deploy contínuo** a partir do GitHub.

5. **Validação Pós-Deploy**  
   - Acesse o domínio configurado e valide o funcionamento das principais rotas.  
   - Teste componentes interativos (**carrinho**, **login**, **checkout**, **modais**).  
   - Verifique o console do navegador e o log do servidor para identificar possíveis erros.  
   - Certifique-se de que o site esteja **responsivo** e com **carregamento otimizado**.

---

### 🐳 Implantação via Docker (opcional)

Para implantar a aplicação usando containers Docker, siga os passos abaixo:

1. Crie um arquivo **Dockerfile** na raiz do projeto:

   ```dockerfile
   # Etapa de build
   FROM node:18-alpine AS builder
   WORKDIR /app
   COPY package*.json ./
   RUN npm install
   COPY . .
   RUN npm run build

   # Etapa de produção
   FROM nginx:alpine
   COPY --from=builder /app/dist /usr/share/nginx/html
   EXPOSE 80
   CMD ["nginx", "-g", "daemon off;"]


A implantação da aplicação distribuída foi planejada para garantir escalabilidade, segurança e facilidade de manutenção em ambientes de produção. Abaixo estão as etapas recomendadas para realizar o deploy do front-end web da TeraBuum.

Etapas de Implantação

### 1. Definição de Requisitos

**Hardware:**
- Servidor ou instância com no mínimo **2 vCPUs**, **2 GB de RAM** e **10 GB de armazenamento**.

**Software:**
- **Node.js** (versão **LTS recomendada**)  
- **NPM** ou **Yarn**  
- **Gerenciador de processos:** PM2 ou **Docker**

**Rede:**
- **Certificado SSL ativo**
- Acesso via **HTTPS** para todas as comunicações

---
### 2. Escolha da Plataforma de Hospedagem

Opte por uma solução de hospedagem confiável que permita fácil **escalabilidade** e **integração contínua (CI/CD)**.

**Opções recomendadas:**
- AWS (**EC2**, **Amplify**, **S3 + CloudFront**)  
- **Vercel**  
- **Netlify**  
- **DigitalOcean**

**Critérios de escolha:**
- Custo-benefício  
- Suporte a **CI/CD**  
- Integração direta com **GitHub**

---

### 3. Configuração do Ambiente

1. **Clone o repositório do projeto:**
   ```bash
   git clone https://github.com/seu-usuario/terabuuum-frontend.git
   cd terabuuum-frontend

Instale as dependências:

npm install


Crie e configure o arquivo .env com variáveis de ambiente (URLs de API, chaves de acesso, etc.).

Compile o projeto para produção:

npm run build


---

## Testes

[Descreva a estratégia de teste, incluindo tipos de teste e ferramentas.]

1. Crie casos de teste cobrindo todos os requisitos funcionais e não funcionais.
2. Implemente testes unitários para funções e classes individuais.
3. Realize testes de integração para verificar a interação entre componentes.
4. Execute testes de carga para avaliar desempenho sob demanda.
5. Utilize frameworks de teste e ferramentas de automação para agilizar o processo.

---

# Referências

- [Documentação do React](https://reactjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [React Router](https://reactrouter.com/)
- [Boas práticas de UX/UI para e-commerce](https://www.made2web.com/blog/10-boas-praticas-de-ux-design-para-implementar-hoje-mesmo)

---

# Planejamento

## Quadro de tarefas

> Divisão de tarefas entre membros do grupo e acompanhamento da execução.

### Semana 1

Atualizado em: 21/04/2024

| Responsável | Tarefa/Requisito | Iniciado em | Prazo | Status | Terminado em |
| :--------- | :--------------- | :---------: | :---: | :----: | :----------- |
| AlunaX     | Introdução       | 01/02/2024  | 07/02/2024 | ✔️ | 05/02/2024 |
| AlunaZ     | Objetivos        | 03/02/2024  | 10/02/2024 | 📝 |             |
| AlunoY     | Histórias de usuário | 01/01/2024 | 07/01/2005 | ⌛ |             |
| AlunoK     | Personas 1       | 01/01/2024  | 12/02/2005 | ❌ |             |

### Semana 2

Atualizado em: 21/04/2024

| Responsável | Tarefa/Requisito | Iniciado em | Prazo | Status | Terminado em |
| :--------- | :--------------- | :---------: | :---: | :----: | :----------- |
| AlunaX     | Página inicial   | 01/02/2024  | 07/03/2024 | ✔️ | 05/02/2024 |
| AlunaZ     | CSS unificado    | 03/02/2024  | 10/03/2024 | 📝 |             |
| AlunoY     | Página de login  | 01/02/2024  | 07/03/2024 | ⌛ |             |
| AlunoK     | Script de login  | 01/01/2024  | 12/03/2024 | ❌ |             |

**Legenda:**

- ✔️: terminado  
- 📝: em execução  
- ⌛: atrasado  
- ❌: não iniciado
