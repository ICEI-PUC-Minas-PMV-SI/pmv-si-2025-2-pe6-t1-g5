# APIs e Web Services

O planejamento de uma aplicação de APIs Web é uma etapa fundamental para o sucesso do projeto. Ao planejar adequadamente, é possível evitar muitos problemas e garantir que a API seja segura, escalável e eficiente. Neste projeto, foram desenvolvidos microserviços independentes que se comunicam entre si para compor uma aplicação de e-commerce robusta, formada pelos seguintes módulos: **UserService (autenticação)**, **VitrineService (catálogo de produtos)**, **EstoqueService**, **CarrinhoService** e **OrderService (pedidos e pagamentos)**.

## Objetivos da API

O objetivo central da API é disponibilizar recursos para que o sistema de e-commerce funcione de maneira integrada e eficiente, permitindo a interação entre o front-end e os microserviços que compõem o backend. Os principais objetivos são:

- Garantir autenticação e autorização de usuários (UserService).
- Disponibilizar catálogo de produtos com listagem, busca e detalhes (VitrineService).
- Controlar e gerenciar níveis de estoque em tempo real (EstoqueService).
- Possibilitar ao usuário criar e gerenciar um carrinho de compras (CarrinhoService).
- Concretizar pedidos e processar pagamentos (OrderService).
- Garantir integração segura, escalável e versionada entre os serviços.


## Modelagem da Aplicação
A aplicação segue a arquitetura de microserviços, com cada serviço responsável por uma funcionalidade específica e se comunicando via APIs REST. A modelagem principal inclui as seguintes entidades:

- **Usuário**: id, nome, email, senha (hash), roles.
- **Produto**: id, nome, descrição, preço, imagens, categoria.
- **Categoria**: id, nome, descrição.
- **Estoque**: produtoId, quantidadeDisponível, reservas.
- **Carrinho**: id, userId, itens (produtoId, quantidade).
- **Pedido**: id, userId, itens, status, valor total, pagamento.

Cada microserviço possui seu próprio banco de dados, garantindo baixo acoplamento e maior escalabilidade. A comunicação ocorre de forma síncrona via REST e, quando necessário, de forma assíncrona com eventos.


## Tecnologias Utilizadas

- **Backend**: Node.js / Express.js.  
- **Banco de Dados**: PostgreSQL (persistência dos microserviços).  
- **Autenticação**: JWT (JSON Web Token).  
- **Documentação**: Swagger / OpenAPI.  
- **Monitoramento**: Prometheus, Grafana.  
- **Logs**: ELK Stack (Elasticsearch, Logstash, Kibana).  
- **Containerização**: Docker e Docker Compose.  
- **Versionamento**: GitHub.  


## API Endpoints

A seguir, os principais endpoints de cada microserviço:

### UserService
- `POST /api/v1/auth/register` – Registrar usuário.  
- `POST /api/v1/auth/login` – Autenticar usuário.  
- `GET /api/v1/auth/me` – Consultar perfil autenticado.  
- `POST /api/v1/auth/logout` – Logout e revogação de token.  

### VitrineService
- `GET /api/v1/vitrine/produtos` – Listar produtos.  
- `GET /api/v1/vitrine/produtos/{id}` – Consultar detalhes de produto.  
- `GET /api/v1/vitrine/categorias` – Listar categorias.  
- `GET /api/v1/vitrine/busca?q=termo` – Buscar produtos.  

### EstoqueService
- `GET /api/v1/estoque/produtos/{id}` – Consultar estoque de um produto.  
- `POST /api/v1/estoque/reservas` – Criar reserva de estoque.  
- `POST /api/v1/estoque/confirmar` – Confirmar baixa de estoque.  
- `POST /api/v1/estoque/liberar` – Liberar reserva.  

### CarrinhoService
- `POST /api/v1/carrinho` – Criar carrinho.  
- `GET /api/v1/carrinho` – Consultar carrinho do usuário.  
- `POST /api/v1/carrinho/itens` – Adicionar item ao carrinho.  
- `PUT /api/v1/carrinho/itens/{id}` – Atualizar item.  
- `DELETE /api/v1/carrinho/itens/{id}` – Remover item.  

### OrderService
- `POST /api/v1/orders` – Criar pedido.  
- `GET /api/v1/orders/{id}` – Consultar pedido.  
- `GET /api/v1/orders` – Listar pedidos do usuário.  
- `POST /api/v1/orders/{id}/cancel` – Cancelar pedido.  
- `POST /api/v1/orders/webhook` – Receber confirmação de pagamento.  

## Considerações de Segurança

- Autenticação obrigatória em endpoints que manipulam dados sensíveis (JWT).  
- Autorização baseada em perfis de acesso (usuário comum vs. administrador).  
- Criptografia de senhas com hash seguro (bcrypt).  
- Comunicação via HTTPS.  
- Rate limiting para mitigar ataques de força bruta.  
- Validação de entrada para prevenir injeções SQL e XSS.

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

- Richardson, C. *Microservices Patterns*. Manning, 2019.  
- Newman, S. *Building Microservices*. O’Reilly, 2021.  
- OpenAPI Specification. https://swagger.io/specification/  
- OWASP API Security Top 10. https://owasp.org/  

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

