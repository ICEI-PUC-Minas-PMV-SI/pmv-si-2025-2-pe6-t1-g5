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
<img width="1061" height="526" alt="supabase-schema-smjdaavxsnbmrdrvejsu" src="https://github.com/user-attachments/assets/660101fe-6743-4ea5-b40d-069eb4d951bf" />

## Tecnologias Utilizadas

- **Backend**: API Web do ASP.NET Core.
- **Banco de Dados**: PostgreSQL (SupaBase).  
- **Autenticação**: JWT (JSON Web Token).  
- **Documentação**: Swagger / OpenAPI.  
- **Versionamento**: GitHub.


## API Endpoints

A seguir, os principais endpoints de cada microserviço:

### UserService
- `POST /api/v1/Users/register` – Registrar usuário.  
- `POST /api/v1/Users/login` – Autenticar usuário.  
- `GET /api/v1/Users` – Consultar todos os perfis (somente Admin.).
- `GET /api/v1/Users/{id}` – Consultar o própio perfil autenticado (todos usuários).  
- `PUT /api/v1/Users/{id}` – Atualizar o seu próprio dado.
- `PUT /api/v1/Users/{id}/role` – Mudar a role dos usuários (somente Admin.).
- `DELETE /api/v1/Users/{id}` – Apagar o seu próprio usuário.

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

### CartService
- `POST /api/v1/cart` – Criar carrinho.  
- `GET /api/v1/cart` – Consultar carrinho do usuário.  
- `PATCH /api/v1/cart/cart-items` – Editar items do carrinho.  
- `PATCH /api/v1/cart/cancel` – Cancelar carrinho.  
- `POST /api/v1/cart/checkout` – Realizar checkout com carrinho.  

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

A implantação da aplicação distribuída é realizada utilizando **containers Docker**, orquestrados por um **Docker Compose**, o que facilita a configuração, execução e escalabilidade dos microserviços em ambientes de produção.

---

## Requisitos de Hardware

**Para um ambiente de produção de pequeno porte:**

| Recurso | Especificação |
|----------|----------------|
| CPU | 4 vCPUs |
| Memória RAM | 8 GB |
| Armazenamento | 40 GB SSD |
| Rede | Conexão estável com acesso à internet (portas 80, 443 e 3306 abertas) |

Em ambientes com maior volume de requisições, recomenda-se ajustar os recursos de CPU e memória conforme a demanda.

---

## Requisitos de Software

| Componente | Versão Recomendada |
|-------------|--------------------|
| Sistema Operacional | Linux (Ubuntu 22.04 LTS ou Amazon Linux 2023) |
| Docker | ≥ 26.x |
| Docker Compose | ≥ v2.x |
| Git | Última versão |
| Nginx (opcional) | Para proxy reverso e balanceamento de carga |
| Banco de Dados | MySQL 8.x (pode ser Amazon RDS ou container dedicado; neste projeto foi utilizado o Supabase) |

---

## Plataforma de Hospedagem

A aplicação pode ser hospedada em diferentes ambientes, de acordo com o nível de disponibilidade desejado:

- AWS EC2 – ideal para ambiente de produção leve ou Free Tier  
- Azure VM ou Google Compute Engine – alternativas equivalentes  
- Servidor Dedicado On-premise – opção local para testes internos  

Em produção, recomenda-se o uso de **AWS EC2 + RDS (MySQL)**, garantindo isolamento entre serviços e maior escalabilidade.

---

## Configuração do Ambiente

### 1. Clonar os repositórios dos microserviços

```bash
git clone https://github.com/TeraBum/microservico-pagamento.git
git clone https://github.com/TeraBum/microservico-estoque.git
git clone https://github.com/TeraBum/microservico-vitrine.git
git clone https://github.com/TeraBum/microservico-carrinho.git
git clone https://github.com/TeraBum/microservico-autenticacao.git
```
2. Configurar variáveis de ambiente (.env)

Cada microserviço possui seu próprio arquivo .env, contendo:
```
DB_HOST=
DB_USER=
DB_PASS=
DB_NAME=
PORT=
JWT_SECRET=
API_KEY=
```
Certifique-se de que os valores estejam corretos e consistentes entre os serviços.

3. Gerar imagens e subir os containers
```
docker compose up -d --build
```

Verifique se os containers estão ativos:
```
docker ps
```

| Serviço         | Porta | URL Swagger                                                                          |
| --------------- | ----- | ------------------------------------------------------------------------------------ |
| UserService     | 5000  | [http://localhost:5000/swagger/index.html](http://localhost:5000/swagger/index.html) |
| Vitrine  | 5010  | [http://localhost:5010/swagger/index.html](http://localhost:5010/swagger/index.html) |
| EstoqueService  | 5020  | [http://localhost:5020/swagger/index.html](http://localhost:5020/swagger/index.html) |
| Carrinho | 5030  | [http://localhost:5030/swagger/index.html](http://localhost:5030/swagger/index.html) |
| OrderService    | 5050  | [http://localhost:5050/swagger/index.html](http://localhost:5050/swagger/index.html) |


### Deploy em Produção EC2

```
Crie uma instância EC2 (t3.micro ou superior) e configure o Security Group liberando as necessárias. (80, 443, configuradas nos Containers...)

Instale o Docker e o Docker Compose conforme os requisitos.

Copie os arquivos da aplicação para o servidor (ou use git pull).
```

Execute:
```
docker compose up -d
```

Utilize o Nginx como proxy reverso, mapeando domínios personalizados (por exemplo, api.sistema.com).

## Testes

### Teste RF-001

Para os testes dessa funcionalidade, foram executadas as requisições HTTP suportadas pelo UserService. As requisições requerem, como medida de segurança.

#### Teste criação de um novo usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/33e66f13-9689-444d-bfa5-87396a9d70c2" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6cba21e7-24b5-4478-8c52-69f1566b9859" />

#### Teste de login do usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/820c9965-cc99-4141-9864-0e800e154c74" />

#### Teste de login de usuário que não existe ou com o password errado:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9c3623ed-e901-40e7-adde-37aeaf05af65" />

#### Teste de um usuário nível "user" ou "manager" buscando os seus próprios dados:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f9b2f4fd-e0f9-45bc-abf9-f01f0333c94a" />

#### Teste de um usuário nível "user" ou "manager" buscando os dados de outro usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/919e7a57-38fd-4dd9-95b9-665c76ec9914" />

#### Teste de um usuário nível "Administrador" buscando os dados de todos os usuários:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e1e71c58-894c-44f4-843a-f8e1758e6db3" />

#### Teste de um usuário nível "user" ou "manager" buscando os dados de todos os usuários:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/64aa85ca-c68c-483f-b03f-b21ee5269aff" />

#### Teste de um usuário nível "user" ou "manager" atualizando os seus própios dados:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4a921aef-1fcc-44e3-85aa-b02d552fcf46" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/116ac953-07dd-4edd-8c14-beb60a474818" />

#### Teste de um usuário nível "user" ou "manager" ou "Administrador" tentando atualizar os seus própios dados com a senha atual errada:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/70e23ecd-94cf-43aa-98f9-cc7ef9f19fad" />

#### Teste de um usuário nível "Administrador" atualizando os dados de outro usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6756deb9-6efa-4e5e-ad48-42431d520d24" />

#### Teste de um usuário nível "Administrador" atualizando o nível de outro usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/76ee4b1c-9185-4f4f-b3b3-12d33e5e13b2" />

#### Teste de um usuário nível "user" ou "manager" atualizando o seu nível de usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f6341f04-4c9e-4511-b82a-c862e589cd0d" />

#### Teste de um usuário nível "Administrador" atualizando o nível de outro usuário para um nível que não existe:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/241f784b-f364-441a-a395-865f55c6a777" />

#### Teste de um usuário nível "user" ou "manager" apagando a conta de um outro usuário:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8bdb6758-da25-4db9-9a5a-f30bc1994af5" />

#### Teste de um usuário nível "user" ou "manager" apagando sua própia conta:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0781d9a6-20cf-46d8-828e-5007f4a61f1e" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fc5da91d-390e-4136-a06c-770c057e1640" />

#### Teste de um usuário nível "Administrador" apagando uma conta qualquer:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/66a470ef-e9b6-4cd7-9abd-1615a859bf2d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9af277c7-e7bf-4cfc-acee-7d293d5d04d5" />

### Teste RF-002

Para os testes dessa funcionalidade, foram executadas as requisições HTTP suportadas pelo EstoqueService. As requisições requerem, como medida de segurança, a função de Administrador para que a API realize as operações.

#### Teste criação de produto e cadastro de produto no estoque:
<img width="1918" height="967" alt="image" src="https://github.com/user-attachments/assets/c37e9558-5947-4837-82b8-b6fed6fd437c" />

#### Teste baixa de estoque para o registro de estoque de um produto:
<img width="1919" height="809" alt="image" src="https://github.com/user-attachments/assets/99dab475-6795-4bb7-9f22-13abb1565c1c" />

#### Teste listagens de estoque, movimentações de estoque, galpões e produtos:
<img width="1911" height="904" alt="image" src="https://github.com/user-attachments/assets/c0b345d3-9094-4f0c-9791-a0a5a96e6fa6" />

## Testes Funcionais VitrineService

### Caso 1: Listar produtos com paginação
- Pré-condição: Produtos cadastrados no sistema.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product?page=1&pageSize=10.
- Resultados esperados: 200 - Retorna TotalItems, Page, PageSize e Products com no máximo 10 itens.
- Endpoint: GET /api/v1/vitrine/product
<img width="1258" height="599" alt="Caso de Teste 1" src="https://github.com/user-attachments/assets/558d9382-1f73-4b93-a256-ee40f15bd94b" />

### Caso 2: Filtrar produtos por categoria
- Pré-condição: Produtos cadastrados pertencentes a categorias.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product?category=Notebooks.
- Resultados esperados: 200 - Todos os produtos retornados possuem Category = Notebooks. Lista vazia se não houver produtos na categoria.
- Endpoint: GET /api/v1/vitrine/product
<img width="1261" height="606" alt="Caso de Teste 2" src="https://github.com/user-attachments/assets/213dbea0-26ae-431c-9908-806ac56f033a" />

### Caso 3: Ordenar produtos por preço
- Pré-condição: Produtos cadastrados com preços e nomes diferentes.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product?sortBy=price&sortOrder=asc.
- Resultados esperados: 200 - Produtos retornados em ordem ascendente de preço. Suporte a sortOrder=asc/desc.
- Endpoint: GET /api/v1/vitrine/product
<img width="1256" height="611" alt="Caso de Teste 3" src="https://github.com/user-attachments/assets/c7f33bac-1beb-4352-ab3c-7ff7dca5e86f" />

### Caso 4: Consultar detalhes de produto existente
- Pré-condição: Produto existente cadastrado.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product/{id} com um id válido.
- Resultados esperados: 200 - Retorna Id, Name, Price, Category, Description, ImagesJson e IsActive.
- Endpoint: GET /api/v1/vitrine/product/{id}
<img width="1250" height="402" alt="Caso de Teste 4" src="https://github.com/user-attachments/assets/03672668-95a8-4e0b-9f2a-a985c1da879e" />

### Caso 5: Consultar produto inexistente
- Pré-condição: Produto inexistente.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product/{id} com um id inválido.
- Resultados esperados: 404 - Produto não encontrado.
- Endpoint: GET /api/v1/vitrine/product/{id}
<img width="1256" height="347" alt="Caso de Teste 6" src="https://github.com/user-attachments/assets/1fb4520a-0b1c-4875-b7cc-a48214c26f58" />

### Caso 6: Consultar estoque de um produto existente
- Pré-condição: Produto existente e vinculado a estoque em StockItems.
- Passo de teste: Faça uma solicitação GET para api/v1/vitrine/product/{id}/stock com um id válido.
- Resultados esperados: 200 - Retorna lista de StockItems com WarehouseId, Quantity e Location. 404 se não houver estoque.
- Endpoint: GET /api/v1/vitrine/product/{id}/stock
<img width="1259" height="386" alt="Caso de Teste 7" src="https://github.com/user-attachments/assets/925e56e5-596c-4edc-be70-caa79c794679" />

## Operações em carrinho de compras
### Caso 1: Obter o carrinho atual se existir
- Pré-condição: Um carrinho ativo deve existir
- Passo de teste: Faça uma solicitação GET para api/v1/cart com o usuário autenticado
- Resultados esperados: 200 - carrinho retornado, 404 se não há carrinho ativo.

  <img width="1378" height="629" alt="Captura de Tela 2025-10-05 às 19 24 40" src="https://github.com/user-attachments/assets/8a84c130-5443-4fbb-aa79-962f3e9194fb" />


### Caso 2: Criar um carrinho
- Pré-condição: Um carrinho ativo não deve existir
- Passo de teste: Faça uma solicitação POST para api/v1/cart com o usuário autenticado e com o corpo do request preenchido.
- Resultados esperados: 200 - carrinho retornado, 400 se há carrinho ativo.

  <img width="1392" height="774" alt="Captura de Tela 2025-10-05 às 20 51 48" src="https://github.com/user-attachments/assets/13c362a2-b203-4f77-9afa-9bd53c5b05da" />

### Caso 3: Editar items do carrinho atual
- Pré-condição: Um carrinho ativo deve existir
- Passo de teste: Faça uma solicitação PATCH para api/v1/cart/cart-items com o usuário autenticado e com o corpo do request contendo os items desejados.
- Resultados esperados: 200 - carrinho retornado, 404 se não há carrinho ativo.

  <img width="1374" height="701" alt="Captura de Tela 2025-10-05 às 20 52 52" src="https://github.com/user-attachments/assets/31853da6-2df7-4fbc-a669-94cdd6d93ca2" />


### Caso 4: Cancelar o carrinho atual
- Pré-condição: Um carrinho ativo deve existir
- Passo de teste: Faça uma solicitação PATCH para api/v1/cart/cancel com o usuário autenticado
- Resultados esperados: 200 - carrinho retornado com o status cancelado, 404 se não há carrinho ativo.

  <img width="1374" height="469" alt="Captura de Tela 2025-10-05 às 20 53 41" src="https://github.com/user-attachments/assets/a1467d9b-9599-46b7-bf02-c6e6e38a46c3" />


### Caso 5: Checkout do carrinho
- Pré-condição: Um carrinho ativo deve existir e deve possuir items
- Passo de teste: Faça uma solicitação post para api/v1/cart/checkout com o usuário autenticado
- Resultados esperados: 200 - carrinho retornado com o status finalizado, 404 se não há carrinho ativo, 400 se o carrinho atual não possuir items ou quantidade de items ultrapassar estoque.

  <img width="1376" height="501" alt="Captura de Tela 2025-10-05 às 20 54 04" src="https://github.com/user-attachments/assets/85f02f98-34d4-4ba0-b198-2ba597ef00d5" />

### Teste relacionados as APIs do micro-serviço Pagamento 
#### Criar pagamento

- Endpoint: POST /api/v1/payments
- Pré-condição: Um pedido válido deve existir no sistema.
- Request body (JSON):

<img width="1310" height="729" alt="image" src="https://github.com/user-attachments/assets/39ba18a1-3001-430a-a9e0-9c30ee55a186" />

- Passo de teste: Executar a requisição POST com dados válidos de pagamento.
- Resultado esperado:
Código HTTP: 201 Created

<img width="1282" height="855" alt="image" src="https://github.com/user-attachments/assets/e04bdedb-9a98-43a7-a000-3302ef45d1bd" />


Retorno com os dados do pagamento, incluindo id, orderId, status e amount.
#### Consultar pagamento por pedido

- Endpoint: GET /api/v1/payments/{orderId}
- Pré-condição: Pagamento associado ao orderId deve existir.
- Passo de teste: Executar a requisição GET passando o orderId.
- Resultado esperado:
Código HTTP: 200 OK
Retorno com os dados do pagamento correspondente ao pedido.

<img width="1279" height="885" alt="image" src="https://github.com/user-attachments/assets/3d00d030-8f74-4a65-ab84-6534b822a017" />
<img width="1284" height="618" alt="image" src="https://github.com/user-attachments/assets/aac5e4a4-6ff0-4668-8aa2-a821c1dc00e7" />

#### Atualizar status do pagamento

- Endpoint: PATCH /api/v1/payments/{paymentId}
- Pré-condição: Pagamento existente no sistema.
- Request body (JSON): PAGO/AGUARDANDO PAGAMENTO/PAGAMENTO NEGADO
<img width="1512" height="170" alt="image" src="https://github.com/user-attachments/assets/d01b7e49-87fe-411a-ade1-4f3818c9c7a8" />

Observação: A API aceita o corpo como string simples contendo o novo status do pagamento.

- Passo de teste: Executar PATCH para atualizar o status do pagamento.
- Resultado esperado:
Código HTTP: 200 OK
- Retorno com os dados do pagamento atualizado, mostrando o novo status.
<img width="1280" height="646" alt="image" src="https://github.com/user-attachments/assets/5867b893-3e9c-405c-b949-3d2b1f257c73" />

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
| Daniela Assis       | Base da API Vitrine   | 20/09/2025    | 29/09/2025 | ✔️    |   29/09/2025              |
| AlunoY        | Histórias de usuário  | 01/01/2024     | 07/01/2005 | ⌛     |                 |
| AlunoK        | Personas 1  |    01/01/2024        | 12/02/2005 | ❌    |       |

#### Semana 2

Atualizado em: 04/10/2025 

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Gabriel Amorim      | Desenvolvimento do Micro-serviço de Pagamento (API)   | 02/10/2025     | 05/10/2025 | ✔️    | 04/10/2025      |
| Daniela Assis       | Conexão da API Vitrine com Supase e Documentação   | 30/09/2025    | 05/10/2025 | ✔️    |   05/10/2025              |
| AlunoY        | Página de login  | 01/02/2024     | 07/03/2024 | ⌛     |                 |
| AlunoK        | Script de login  |  01/01/2024    | 12/03/2024 | ❌    |       |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado
