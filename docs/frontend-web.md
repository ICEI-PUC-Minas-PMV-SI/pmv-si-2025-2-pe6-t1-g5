# Front-end Web

**TeraBum – Plataforma de E-commerce**

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
#### HOME
<img width="1024" height="1536" alt="ChatGPT Image 2 de nov  de 2025, 20_53_33" src="https://github.com/user-attachments/assets/e6789cf2-c93a-43f3-98ea-220cdc704304" />

##### PRODUTOS
<img width="1024" height="1536" alt="ChatGPT Image 2 de nov  de 2025, 21_18_05" src="https://github.com/user-attachments/assets/39cefeca-9733-4384-ae61-becb8d607e89" />

---

### Design Visual
<img width="4000" height="2250" alt="TeraBum-1" src="https://github.com/user-attachments/assets/0019ed26-c25a-4507-8dcb-9d520d477daa" />

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
<img width="1058" height="471" alt="Fluxo de Dados" src="https://github.com/user-attachments/assets/20bedc8b-bd59-4f7d-945e-0d22729cb5cd" />

**O fluxo de dados acima representa o caminho percorrido pelo usuário desde o acesso inicial até a finalização da compra:**

**1. Home:** ponto de entrada do site, onde o usuário pode navegar para a página de produtos.

**2. Produtos:** exibe o catálogo de itens disponíveis. O usuário pode visualizar detalhes específicos de cada produto.

**3. Detalhes do Produto:** apresenta informações mais completas (descrição, preço, estoque) e permite adicionar o item ao Carrinho.

**4. Carrinho:** reúne os produtos selecionados e direciona o usuário para o processo de Login/Criação de Conta antes de prosseguir com o pagamento.

**5. Login/Criar Conta:** se o usuário ainda não estiver autenticado, ele precisa se registrar ou entrar em sua conta.
  
  **5.1 Sim:** após login bem-sucedido, o usuário é redirecionado para a etapa de Pagamento.
 
  **5.2 Não:** pode optar por Continuar comprando, retornando à página de Produtos.
  
**6.** Pagamento: etapa final, onde o usuário insere as informações de pagamento e conclui o pedido.
   
Esse fluxo garante uma navegação intuitiva e orientada, facilitando o processo de compra e promovendo a conversão no e-commerce.

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
   git clone https://github.com/seu-usuario/terabum-frontend.git
   cd terabum-frontend

Instale as dependências:

npm install


Crie e configure o arquivo .env com variáveis de ambiente (URLs de API, chaves de acesso, etc.).

Compile o projeto para produção:

npm run build


---

## Testes
### API VitrineService

**Caso de Teste 1 – Busca de Produto na Home**

**Objetivo:**  
Verificar se o usuário consegue buscar por um produto (exemplo: *notebook*) na barra de pesquisa da página inicial e obter resultados correspondentes.

| Item | Descrição |
|------|------------|
| **Tipo de teste** | Funcional / Integração |
| **Pré-condições** | Página Home carregada corretamente. Conexão com a API de produtos ativa. |
| **Passos** | 1. Acessar a página Home.<br>2. Localizar a barra de busca.<br>3. Digitar “notebook” e pressionar Enter.<br>4. Aguardar exibição dos resultados. |
| **Resultado Esperado** | A página deve exibir produtos cujo nome ou descrição contenha o termo “notebook”. Nenhum erro deve ser apresentado. |

Evidência:

<img width="789" height="545" alt="Captura de Tela 2025-11-02 às 21 52 25" src="https://github.com/user-attachments/assets/91389713-d95e-4b29-b446-2062e6be5a44" />

---

**Caso de Teste 2 – Filtro por Categoria na Home**

**Objetivo:**  
Validar se, ao clicar em uma categoria (exemplo: *Eletrônicos*), o usuário é redirecionado para a página de produtos com o filtro aplicado automaticamente.

| Item | Descrição |
|------|------------|
| **Tipo de teste** | Funcional / Integração |
| **Pré-condições** | Página Home carregada. Categorias listadas e clicáveis. |
| **Passos** | 1. Acessar a página Home.<br>2. Clicar na categoria “Hardware”.<br>3. Verificar o redirecionamento para a página de produtos.<br>4. Conferir se apenas produtos da categoria “Hardware” estão visíveis. |
| **Resultado Esperado** | O usuário é redirecionado para a página de produtos, que exibe apenas itens da categoria selecionada. |

Evidência:
<img width="1368" height="358" alt="Captura de Tela 2025-11-02 às 21 38 27" src="https://github.com/user-attachments/assets/89c065d1-8053-4809-bd46-74c0e983af58" />
Depois de clicar em celulares
<img width="1381" height="511" alt="Captura de Tela 2025-11-02 às 21 37 09" src="https://github.com/user-attachments/assets/a3182935-a166-4e40-9021-9f07cabd3ac8" />





---

**Caso de Teste 3 – Ordenação e Filtro de Preço na Página de Produtos**

**Objetivo:**  
Garantir que a funcionalidade de ordenação e filtro de preço funcionem corretamente.

| Item | Descrição |
|------|------------|
| **Tipo de teste** | Funcional / Integração |
| **Pré-condições** | Página de produtos carregada com a lista completa. |
| **Passos** | 1. Acessar a página de produtos.<br>2. Selecionar a opção de ordenação “Preço: menor para maior”.<br>3. Definir o filtro de preço máximo em **R$1000**.<br>4. Aplicar o filtro e verificar os resultados. |
| **Resultado Esperado** | A listagem deve mostrar apenas produtos com valor até **R$1000**, ordenados do menor para o maior preço. Nenhum erro deve ocorrer na interface. |

Evidência:
<img width="1392" height="494" alt="Captura de Tela 2025-11-02 às 21 49 41" src="https://github.com/user-attachments/assets/f57ca2f3-3933-426e-b3e4-cbd88a88a001" />



---
**Caso de Teste 4 – Login de admin e teste crud de itens de estoque e produtos**

**Objetivo:**  
Garantir que a funcionalidade de crud de estoque e de produto funciona e está protegida por autenticação.

| Item | Descrição |
|------|------------|
| **Tipo de teste** | Funcional / Integração |
| **Pré-condições** | Login com role de "Administrador" |
| **Passos** | 1. Acessar a página de login.<br>2. Realizar operações de crud de item de estoque.<br>3. Realizar operações de crud de item de estoque.<br>4. Validar sessão via aba anônima. |
| **Resultado Esperado** | Criação, edição e exclusão de itens de estoque e produtos após login bem sucedido. |

Vídeo evidência do teste:
https://github.com/user-attachments/assets/b371da78-787c-41c1-8860-66f42ee0753a


---
**Caso de Teste 5 – Adicionar item ao carrinho**

**Objetivo:**  
Verificar se o usuário consegue adicionar um item ao carrinho

| Item                   | Descrição                                                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Tipo de teste**      | Funcional / Integração                                                                                                         |
| **Pré-condições**      | Usuário logado                                                                                                                 |
| **Passos**             | 1. Acessar a página de Produtos<br>2. Localizar o produto desejado<br>3. Clicar em Adicionar ao Carrinho.                      |
| **Resultado Esperado** | A interface irá notifcar o usuário que o produto foi adicionado e<br>a tela de carrinho agora irá exibir o carrinho com o item |

Evidência:

<img width="1068" height="556" alt="Captura de Tela 2025-11-02 às 22 02 28" src="https://github.com/user-attachments/assets/0611bc80-7df4-4858-8b2a-2fa40db23dcb" />

---
**Caso de Teste 6 – Fazer checkout do carrinho**

**Objetivo:**  
Verificar se o usuário consegue realizar o checkout

| Item                   | Descrição                                                            |
| ---------------------- | -------------------------------------------------------------------- |
| **Tipo de teste**      | Funcional / Integração                                               |
| **Pré-condições**      | Usuário com carrinho ativo                                           |
| **Passos**             | 1. Acessar a página de carrinho<br>2. Clicar em Finalizar Compra<br> |
| **Resultado Esperado** | A interface irá notifcar o usuário que o carrinho foi finalizado     |

Evidência:

<img width="1359" height="444" alt="Captura de Tela 2025-11-02 às 22 08 55" src="https://github.com/user-attachments/assets/02639faf-4198-4842-8b81-4bcde1bb8440" />


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

Atualizado em: 26/10/2025

| Responsável | Tarefa/Requisito | Iniciado em | Prazo | Status | Terminado em |
| :--------- | :--------------- | :---------: | :---: | :----: | :----------- |
| Daniela Assis| Kit de Marca e Wireframes Front-end  | 20/10/2025  | 26/10/2025 | ✔️ | 26/10/2025 |
| AlunaZ     | Objetivos        | 03/02/2024  | 10/02/2024 | 📝 |             |
| AlunoY     | Histórias de usuário | 01/01/2024 | 07/01/2005 | ⌛ |             |
| AlunoK     | Personas 1       | 01/01/2024  | 12/02/2005 | ❌ |             |

### Semana 2

Atualizado em: 02/11/2025

| Responsável | Tarefa/Requisito | Iniciado em | Prazo | Status | Terminado em |
| :--------- | :--------------- | :---------: | :---: | :----: | :----------- |
| Daniela Assis| Páginas Home e Produtos, Navbar e Footer, e Slides de Apresentação | 27/10/2025 | 02/11/2025 | ✔️ | 02/11/2025 |
| AlunaZ     | CSS unificado    | 03/02/2024  | 10/03/2024 | 📝 |             |
| AlunoY     | Página de login  | 01/02/2024  | 07/03/2024 | ⌛ |             |
| AlunoK     | Script de login  | 01/01/2024  | 12/03/2024 | ❌ |             |

**Legenda:**

- ✔️: terminado  
- 📝: em execução  
- ⌛: atrasado  
- ❌: não iniciado
