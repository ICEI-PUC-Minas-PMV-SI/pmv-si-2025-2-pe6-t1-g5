# Front-end Web

TeraBuum – Plataforma de E-commerce

Projeto de interface web para uma plataforma de e-commerce voltada para venda de produtos de informática, como kits de hardware, periféricos e acessórios. O objetivo é fornecer uma experiência de compra moderna, intuitiva e responsiva, permitindo que o usuário visualize produtos, adicione itens ao carrinho, escolha métodos de pagamento e finalize pedidos de forma segura.

## Projeto da Interface Web

Projeto da Interface Web

A interface foi desenvolvida em React, com foco em usabilidade e design responsivo. Principais características:

Layout baseado em grid: Páginas com áreas principais para conteúdo, resumo do pedido e sidebar flutuante para informações importantes.

Interações do usuário: Modal de alteração de endereço, dropdown para escolha de métodos de pagamento, seleção de parcelas para cartões e alertas de confirmação de ações.

Páginas principais: Home, Produtos, Carrinho, Pagamento, Pedidos, Detalhes do Pedido, Login, Registro e Admin de Estoque.

Componentes reutilizáveis: Navbar, Footer, ProductCard, Loader.

### Wireframes

[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

### Design Visual

Design Visual

Paleta de cores:

Primary: #24DBC5 → usada em botões de ação, destaques e links importantes.

Secondary: #E8EEF5 → usada para backgrounds de cards, seções e elementos de destaque secundário.

Black: #000000 → usada para textos principais e ícones.

Tipografia:

Fonte principal: Prompt, sans-serif

Títulos, textos e botões seguem consistência de fonte para manter identidade visual.

Estilo dos componentes:

Botões: Bordas arredondadas, cores primárias e efeito hover (hover:bg-[#1bb3a3]).

Cards e seções: Fundo secundário (#E8EEF5) ou branco (#ffffff) com sombra (shadow) e cantos arredondados (rounded-lg).

Inputs e selects: Bordas arredondadas, padding interno (p-2 ou p-3) e cores neutras de fundo (white ou secondary).

Modal de endereço: Fundo branco, cantos arredondados, sombra e sobreposição semi-transparente (bg-black bg-opacity-50).

Componentes reutilizáveis: Navbar, Footer, cards de produto, sidebar flutuante para resumo de pedido, botões e modais.

Consistência visual: Todas as páginas mantêm padrão de header (Navbar), footer, cores e tipografia, garantindo experiência unificada para o usuário.

## Fluxo de Dados

[Diagrama ou descrição do fluxo de dados na aplicação.]

## Tecnologias Utilizadas
React.js com TypeScript

Tailwind CSS para estilização

React Router para navegação entre páginas

Serviços simulados via CartService e VitrineService (API mock)

Git/GitHub para versionamento

## Considerações de Segurança

Autenticação e autorização: Controle de acesso para páginas de admin e ações sensíveis.

Proteção de dados sensíveis: Cartões de crédito mascarados e informações pessoais protegidas.

SSL/TLS: Todas as transações devem ser feitas via HTTPS.

Validação de entrada: Inputs de formulário validados no frontend antes de enviar ao backend.
## Implantação

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.
5. Realize testes para garantir que a aplicação esteja funcionando corretamente no ambiente de produção.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Documentação do React: https://reactjs.org/

Tailwind CSS: https://tailwindcss.com/

React Router: https://reactrouter.com/

Boas práticas de UX e UI para e-commerce

# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

### Semana 1

Atualizado em: 21/04/2024

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| AlunaX        | Introdução | 01/02/2024     | 07/02/2024 | ✔️    | 05/02/2024      |
| AlunaZ        | Objetivos    | 03/02/2024     | 10/02/2024 | 📝    |                 |
| AlunoY        | Histórias de usuário  | 01/01/2024     | 07/01/2005 | ⌛     |                 |
| AlunoK        | Personas 1  |    01/01/2024        | 12/02/2005 | ❌    |       |

#### Semana 2

Atualizado em: 21/04/2024

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| AlunaX        | Página inicial   | 01/02/2024     | 07/03/2024 | ✔️    | 05/02/2024      |
| AlunaZ        | CSS unificado    | 03/02/2024     | 10/03/2024 | 📝    |                 |
| AlunoY        | Página de login  | 01/02/2024     | 07/03/2024 | ⌛     |                 |
| AlunoK        | Script de login  |  01/01/2024    | 12/03/2024 | ❌    |       |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

