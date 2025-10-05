# APIs e Web Services

O planejamento de uma aplicação de APIs Web é uma etapa fundamental para o sucesso do projeto. Ao planejar adequadamente, é possível evitar muitos problemas e garantir que a API seja segura, escalável e eficiente. Neste projeto, foram desenvolvidos microserviços independentes que se comunicam entre si para compor uma aplicação de e-commerce robusta, formada pelos seguintes módulos: **UserService (autenticação)**, **VitrineService (catálogo de produtos)**, **EstoqueService (gerenciar estoque, movimentações e produtos)**, **CarrinhoService** e **OrderService (pedidos e pagamentos)**.

## Objetivos da API

O objetivo central da API é disponibilizar recursos para que o sistema de e-commerce funcione de maneira integrada e eficiente, permitindo a interação entre o front-end e os microserviços que compõem o backend. Os principais objetivos são:

- Garantir autenticação e autorização de usuários (UserService).
- Disponibilizar catálogo de produtos com listagem, busca e detalhes (VitrineService).
- Controlar e gerenciar níveis de estoque e cadastrar produtos. (EstoqueService).
- Possibilitar ao usuário criar e gerenciar um carrinho de compras (CarrinhoService).
- Concretizar pedidos e processar pagamentos (OrderService).
- Garantir integração segura, escalável e versionada entre os serviços.


## Modelagem da Aplicação
A aplicação segue a arquitetura de microserviços, com cada serviço responsável por uma funcionalidade específica e se comunicando via APIs REST. A modelagem principal inclui as seguintes entidades:

- **Usuário**: id, nome, email, senha (hash), roles.
- **Product**: Id (uuid), Name (string), Description (string), Price (integer), ImagesJson (string/json), Category (string), IsActive (boolean), CreatedAt (timestamp).
- **StockItems**: ProductId (uuid), WarehouseId (uuid), Quantity (integer), Reserved (integer), UpdatedAt (timestamp).
- **StockMoves**: Id (uuid), ProductId (uuid), WarehouseId (uuid), QtyMoved (integer), Reason(string), CreatedAt (timestamp).
- **Warehouse**: Id (uuid), Name (string), Location (string), CreatedAt (timestamp). 
- **Categoria**: id, nome, descrição.
- **Carrinho**: id, userId, itens (produtoId, quantidade).
- **Pedido**: id, userId, itens, status, valor total, pagamento.

Cada microserviço é encarregado de expor os endpoints para a manipulação das estruturas de dados definidas acima. Essa manipulação é a criação, alteração, deleção e recuperação desses dados persistidos em banco de dados.

## Tecnologias Utilizadas

- **Backend**: API Web do ASP.NET Core.
- **Banco de Dados**: PostgreSQL (SupaBase).  
- **Autenticação**: JWT (JSON Web Token).  
- **Documentação**: Swagger / OpenAPI.  
- **Versionamento**: GitHub.


## API Endpoints

A seguir, os principais endpoints de cada microserviço:

### UserService
- `POST /api/v1/auth/register` – Registrar usuário.  
- `POST /api/v1/auth/login` – Autenticar usuário.  
- `GET /api/v1/auth/me` – Consultar perfil autenticado.  
- `POST /api/v1/auth/logout` – Logout e revogação de token.

### VitrineService
- `GET /api/v1/vitrine/Product` – Listar produtos.
- `GET /api/v1/vitrine/Product/{id}` – Consultar detalhes de produto.
- `GET /api/v1/vitrine/Product/{id}/stock` – Consultar estoque de um produto específico.

### EstoqueService

#### StockItems (Estoque de produto)
- `GET /api/v1/stock-items` – Listar estoque de produtos.
- `GET /api/v1/stock-items/{warehouseId}/{productId}` – Consultar estoque de um produto.
- `PUT /api/v1/stock-items/{warehouseId}/{productId}` – Atualizar estoque de um produto.
- `DELETE /api/v1/stock-items/{warehouseId}/{productId}` – Deleta o estoque de um produto. 
- `POST /api/v1/stock-items` – Criar item de estoque.  
- `POST /api/v1/stock-items/baixa` – Confirmar baixa de estoque.  

#### StockMoves (Movimentação de estoque)
- `GET /api/v1/stock-moves` – Listar movimentações de estoque.
- `GET /api/v1/stock-moves/{id}` – Consultar movimentação de estoque.
- `GET /api/v1/stock-moves/by-product/{productId}` – Listar movimentações de estoque filtrando por produto. 
- `GET /api/v1/stock-moves/by-warehouse/{warehouseId}` – Listar movimentações de estoque filtrando por galpão.
- `GET /api/v1/stock-moves/by-warehouse-product/{warehouseId}/{productId}` – Listar movimentações de estoque filtrando por galpão e produto.

#### Product (Produto)
- `POST /api/v1/product` – Criar produto.
- `GET /api/v1/product` – Listar produtos.
- `GET /api/v1/product/{id}` – Consultar daos de um produto.
- `PUT /api/v1/product/{id}` – Atualizar dados de um produto.
- `DELETE /api/v1/product/{id}` – Deletar um produto.

#### Warehouse (Galpão)
- `POST /api/v1/warehouse` – Criar galpão.
- `GET /api/v1/warehouse` – Listar galpões.
- `GET /api/v1/warehouse/{id}` – Consultar daos de um galpão.
- `PUT /api/v1/warehouse/{id}` – Atualizar dados de um galpão.
- `DELETE /api/v1/warehouse/{id}` – Deletar um galpão.

### CarrinhoService
- `POST /api/v1/carrinho` – Criar carrinho.  
- `GET /api/v1/carrinho` – Consultar carrinho do usuário.  
- `POST /api/v1/carrinho/itens` – Adicionar item ao carrinho.  
- `PUT /api/v1/carrinho/itens/{id}` – Atualizar item.  
- `DELETE /api/v1/carrinho/itens/{id}` – Remover item.  

### OrderService

- `POST /api/v1/payments` – Criar pagamento
- `GET /api/v1/payments/{orderId}` – Consultar pagamento por pedido  
- `PATCH /api/v1/payments/{paymentId}` – Atualizar status do pagamento  
- `DELETE /api/v1/payments/{paymentId}` – Cancelar pagamento  

## Considerações de Segurança

- Autenticação obrigatória em endpoints que manipulam dados sensíveis (JWT).  
- Autorização baseada em perfis de acesso (usuário comum vs. administrador).  
- Criptografia de senhas com hash seguro (bcrypt).  
- Comunicação via HTTPS.  
- Rate limiting para mitigar ataques de força bruta.  
- Validação de entrada para prevenir injeções SQL e XSS.

## Implantação

A implantação da aplicação distribuída é realizada utilizando containers Docker, orquestrados por um Docker Compose, o que facilita a configuração, execução e escalabilidade dos microserviços em ambientes de produção.

 ## Requisitos de Hardware

Para um ambiente de produção de pequeno porte:

CPU: 4 vCPUs

Memória RAM: 8 GB

Armazenamento: 40 GB SSD

Rede: Conexão estável com acesso à internet (porta 80, 443 e 3306 abertas)

Para ambientes com maior volume de requisições, recomenda-se ajustar os recursos de CPU e memória conforme a demanda.

 ## Requisitos de Software

Sistema Operacional: Linux (Ubuntu 22.04 LTS ou Amazon Linux 2023)

Docker: ≥ 26.x

Docker Compose: ≥ v2.x

Git: para clonagem dos repositórios

Nginx (opcional): como proxy reverso e balanceador de carga

Banco de Dados: MySQL 8.x (pode ser RDS ou container dedicado, estamos usando Supabase)

 ## Plataforma de Hospedagem

A aplicação pode ser hospedada em:

AWS EC2 (Free Tier ou produção leve)

Azure VM ou Google Compute Engine

Servidores dedicados on-premise


 ## Configuração do Ambiente

Clonar os repositórios dos microserviços:

git clone https://github.com/seu-org/microservico-usuarios.git
git clone https://github.com/seu-org/microservico-vitrine.git
git clone https://github.com/seu-org/microservico-estoque.git
git clone https://github.com/seu-org/microservico-carrinho.git
git clone https://github.com/seu-org/microservico-pedido.git
git clone https://github.com/seu-org/microservico-pagamento.git


Configurar variáveis de ambiente (.env)
Cada microserviço possui seu arquivo .env contendo:

Credenciais do banco (DB_HOST, DB_USER, DB_PASS, DB_NAME)

Porta de execução (PORT)

Tokens e chaves de API, se aplicável

Gerar imagem e subir containers:

docker compose up -d --build


## Verificar containers ativos:

docker ps


Acesso aos serviços, é necessário ajustar as portas utilizadas por cada container/API

UserService → http://localhost:xxxx/swagger/index.html

VitrineService → http://localhost:xxxx/swagger/index.html

EstoqueService → http://localhost:xxxx/swagger/index.html

CarrinhoService → http://localhost:xxxx/swagger/index.html

OrderService → http://localhost:xxxx/swagger/index.html

PaymentService → http://localhost:xxxx/swagger/index.html

 ## Deploy em Produção

Crie uma instância EC2 (t3.micro ou superior) e configure o Security Group liberando as portas 80 e 443.

Instale Docker e Docker Compose conforme os requisitos.

Copie os arquivos da aplicação (ou utilize git pull direto no servidor).

Execute docker compose up -d para iniciar todos os serviços.

Utilize Nginx como proxy reverso para mapear domínios personalizados (ex: api.sistema.com).


 ## Testes Pós-Implantação

Após o deploy:

Verifique se todos os containers estão “healthy” via docker ps.

Acesse cada endpoint /swagger e valide o funcionamento das rotas.

Realize um fluxo completo (criar usuário → adicionar produto → criar pedido → efetuar pagamento).

Monitore logs via docker logs <container> para garantir estabilidade e comunicação entre serviços.

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

Atualizado em: 29/09/2025

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Gabriel Amorim       | Criação do Trello e repositórios das APIs do Git da TeraBUM | 29/09/2025     | 01/10/2025 | ✔️    | 01/10/2025      |
| AlunaZ        | Objetivos    | 03/02/2024     | 10/02/2024 | 📝    |                 |
| AlunoY        | Histórias de usuário  | 01/01/2024     | 07/01/2005 | ⌛     |                 |
| AlunoK        | Personas 1  |    01/01/2024        | 12/02/2005 | ❌    |       |

#### Semana 2

Atualizado em: 04/10/2025 

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Gabriel Amorim      | Desenvolvimento do Micro-serviço de Pagamento (API)   | 02/10/2025     | 05/10/2025 | ✔️    | 04/10/2025      |
| AlunaZ        | CSS unificado    | 03/02/2024     | 10/03/2024 | 📝    |                 |
| AlunoY        | Página de login  | 01/02/2024     | 07/03/2024 | ⌛     |                 |
| AlunoK        | Script de login  |  01/01/2024    | 12/03/2024 | ❌    |       |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

