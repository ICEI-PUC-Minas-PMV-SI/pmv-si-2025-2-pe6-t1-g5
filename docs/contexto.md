# Introdução

O avanço da tecnologia e a crescente digitalização do comércio têm impulsionado o desenvolvimento de soluções inovadoras para o setor de vendas online. Neste contexto, o projeto TeraBum propõe a criação de um software de e-commerce especializado na comercialização de produtos eletrônicos, utilizando uma arquitetura distribuída para garantir escalabilidade, desempenho e confiabilidade. O objetivo é atender às demandas de consumidores cada vez mais exigentes, oferecendo uma plataforma robusta, segura e eficiente.

## Problema

A crescente demanda por produtos eletrônicos no mercado digital tem revelado desafios significativos para empresas que atuam no setor de e-commerce. Muitos sistemas atuais enfrentam dificuldades relacionadas à escalabilidade, lentidão em períodos de pico, falhas na integração entre serviços e limitações na personalização da experiência do usuário. Além disso, consumidores esperam plataformas que ofereçam navegação fluida, segurança nas transações e suporte eficiente. O contexto tecnológico atual exige soluções que sejam capazes de lidar com grandes volumes de dados e acessos simultâneos, o que torna essencial o uso de arquiteturas distribuídas. O projeto será desenvolvido considerando esse cenário, com foco em empresas que comercializam eletrônicos e buscam modernizar sua infraestrutura digital.

## Objetivos

Objetivo Geral:
Desenvolver um software de e-commerce com arquitetura distribuída, voltado para a venda de produtos eletrônicos, que ofereça alta disponibilidade, escalabilidade e uma experiência de usuário otimizada.
Objetivos Específicos:
- Implementar uma arquitetura baseada em microserviços para garantir modularidade e facilidade de manutenção.
- Integrar sistemas de pagamento e logística de forma eficiente e segura.
- Desenvolver funcionalidades que permitam personalização da interface e recomendação de produtos com base em comportamento de compra.

## Justificativa
A escolha por desenvolver um software de e-commerce com arquitetura distribuída se justifica pela necessidade de atender às exigências do mercado atual, que demanda soluções escaláveis, resilientes e adaptáveis. O setor de eletrônicos, em especial, apresenta alto volume de transações e constante atualização de produtos, o que exige uma plataforma flexível e robusta. Além disso, a arquitetura distribuída permite que diferentes partes do sistema sejam desenvolvidas e escaladas de forma independente, reduzindo riscos e melhorando o desempenho. A proposta também visa proporcionar uma experiência de compra mais fluida e personalizada, aumentando a competitividade da empresa TeraBum no mercado digital.

## Público-Alvo

O público-alvo da aplicação inclui consumidores com perfil tecnológico, interessados em adquirir produtos eletrônicos de forma prática e segura. São usuários que possuem familiaridade com plataformas digitais, valorizam a agilidade nas compras e esperam interfaces intuitivas. Além dos clientes finais, o sistema será utilizado por administradores da loja, responsáveis pela gestão de produtos, pedidos e atendimento. Esses usuários possuem conhecimento intermediário em tecnologia e atuam em ambientes organizacionais com hierarquias definidas. A compreensão desses perfis é essencial para o desenvolvimento de funcionalidades adequadas e uma experiência de uso eficiente.

# Especificações do Projeto

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto.

A priorização dos requisitos foram determinadas a partir do que é considerado essencial para o funcionamento mínimo da plataforma. Desse modo, prioridade ALTA é o que é considerado essencial e BAIXA são funcionalidades adicionais que podem serem implentadas mais tarde no desenvolvimento.

O objetido dessa priorização é ter um produto mínimo viável (PMV) que possa atingir os escopos do projeto de maneira satisfatória o mais rápido possível.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| CRUD de usuário, sendo esse mesmo podendo ser administrador ou normal. Isso inclui cadastro de usuário externo como também criação de contas de admin | ALTA | 
|RF-002| CRUD de items a serem vendidos, que é gerenciado por usuários administradores por um painel, levando em conta inventários dos mesmos   | ALTA |
|RF-003| Um usuário que comprou um item pode deixar um review no mesmo.   | BAIXA |
|RF-004| Um usuário pode buscar dentro da aplicação por items desejados, sendo essa busca tanto por filtros quando por similaridade de texto.   | ALTA |
|RF-005| Um usuário pode criar um carrinho de compras com os items desejados e ir ao checkout. O carrinho deve levar em consideração o inventário de items, notificando o usuário caso hajam mudanças pertinentes (EX: estoque acabou).   | ALTA |
|RF-006| Um usuário pode pagar a sua compra usando o(s) provedor(es) de pagamento   | ALTA |
|RF-007| O usuário deve ser notificado quanto sua transação for concluída   | MÉDIA |
|RF-008| O usuário deve ser capaz de ver suas compras, incluindo status e localização.    | MÉDIA |
|RF-009| Um usuário administrador deve ser capaz de gerar relatórios de vendas do sistema.   | BAIXA |
|RF-010| Um usuário administrador deve ser capaz de cadastrar outros usuários administradores.    | BAIXA |
|RF-011| Um usuário administrador deve ser capaz de administrar a contas e pedidos de usuários comuns para lidar com eventuais problemas, esses alterações devem possuir rastreabilidade.    | BAIXA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| A aplicação deve ser de fácil entendimento para o usuário consumidor, sendo o objetivo final do sistema a compra de produtos desejados de maneira rápida e sem entraves.  | ALTA | 
|RNF-002| O tempo de resposta da aplicação deve ser de , no mínimo, 100ms. |  MÉDIA | 
|RNF-003| A aplicação deve ser disponibilizada tanto para web quanto para mobile.  |  ALTA | 
|RNF-004| A aplicação deve ser segura, usando as boas práticas de segurança e não abrindo brechas de vazamento de dados de usuários. |  ALTA | 
|RNF-005| A aplicação deve ser escalável de maneira que possa atender eventuais picos e se adaptar a um constante crescimento de seus usuários. |  MÉDIA | 
|RNF-006| A aplicação deve ter um uptime de 95% ao ano.  |  MÉDIA | 
|RNF-007| A aplicação deve ser de fácil manutenção tanto para corrigir erros quanto para extender suas funcionalidades. |  MÉDIA | 

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend        |

Enumere as restrições à sua solução. Lembre-se de que as restrições geralmente limitam a solução candidata.

> **Links Úteis**:
> - [O que são Requisitos Funcionais e Requisitos Não Funcionais?](https://codificar.com.br/requisitos-funcionais-nao-funcionais/)
> - [O que são requisitos funcionais e requisitos não funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/)

# Catálogo de Serviços
Aplicação desenvolvida com **Next.js** (front-end), **Node.js + TypeScript** (back-end) e banco de dados gratuito (**Supabase, Railway ou PlanetScale**), com hospedagem na **Vercel**.

---

## Serviços Principais

### 1. Cadastro e Autenticação
- Registro e login de usuários (clientes e administradores).
- Autenticação segura com **JWT**.

- Armazenamento de credenciais e dados no banco de dados.

### 2. Catálogo de Produtos
- Listagem e detalhamento de produtos (nome, descrição, preço, estoque, imagens).
- Filtros por categoria e preço.
- Gerenciamento de produtos pelo administrador.

### 3. Carrinho de Compras
- Adição, remoção e atualização de produtos.

- Persistência do carrinho para usuários autenticados.

### 4. Processamento de Pedidos
- Criação e gestão de pedidos.
- Atualização de status (pendente, pago, enviado, entregue).
- Histórico de pedidos para clientes.

### 5. Administração e Gestão 
- Painel administrativo para produtos, pedidos e usuários.
- Relatórios de vendas e controle de estoque.
- Gerenciamento de permissões.

## Observações Técnicas
- **Deploy automático:** a cada push no GitHub, a Vercel realiza o deploy contínuo da aplicação.
- **Serverless:** não há acesso direto a servidores ou containers; escalabilidade e disponibilidade são gerenciadas pela plataforma.
- **Variáveis de ambiente:** configuradas diretamente na Vercel, garantindo segurança das credenciais e integrações.


# Arquitetura da Solução

Definição de como o software é estruturado em termos dos componentes que fazem parte da solução e do ambiente de hospedagem da aplicação.

![arq](https://github.com/user-attachments/assets/b9402e05-8445-47c3-9d47-f11696e38a3d)


## Tecnologias Utilizadas

Descreva aqui qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas.

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.

## Hospedagem

A hospedagem da aplicação foi realizada na plataforma Vercel, escolhida por sua integração nativa com projetos desenvolvidos em Next.js e por oferecer um ambiente serverless com escalabilidade automática, simplificando o processo de deploy e manutenção.

O fluxo de hospedagem ocorre da seguinte forma:

- O código-fonte da aplicação é versionado em um repositório no GitHub.

- O repositório é integrado diretamente à Vercel, permitindo que a cada novo push seja gerado automaticamente um novo deploy.

- O deploy contínuo (CI/CD) é configurado pela própria plataforma, dispensando a necessidade de acesso via SSH ou gerenciamento manual de servidores, como seria necessário em ambientes tradicionais (ex.: AWS EC2).

- Variáveis de ambiente (como chaves de API e credenciais de banco de dados, ex.: Supabase, Railway ou PlanetScale) são definidas no painel da Vercel, garantindo segurança e isolamento de informações sensíveis.

A Vercel gera automaticamente uma URL pública para a aplicação (ex.: https://nomedoprojeto.vercel.app), além da possibilidade de vincular domínios personalizados.

Benefícios da Hospedagem na Vercel

- Deploys rápidos e automatizados a partir do GitHub.

- Integração nativa com Next.js, otimizando performance.

- Ambiente serverless, eliminando a necessidade de configuração manual de servidores ou containers.

- Escalabilidade automática conforme a demanda de acessos.

- Monitoramento simplificado de logs e status da aplicação via painel da Vercel.

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
