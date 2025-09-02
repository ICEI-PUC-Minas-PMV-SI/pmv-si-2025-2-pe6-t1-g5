# Introdução

O avanço da tecnologia e a crescente digitalização do comércio têm impulsionado o desenvolvimento de soluções inovadoras para o setor de vendas online. Neste contexto, o projeto TeraBum propõe a criação de um software de e-commerce especializado na comercialização de produtos eletrônicos, utilizando uma arquitetura distribuída para garantir escalabilidade, desempenho e confiabilidade. O objetivo é atender às demandas de consumidores cada vez mais exigentes, oferecendo uma plataforma robusta, segura e eficiente.

## Problema

A crescente demanda por produtos eletrônicos no mercado digital tem revelado desafios significativos para empresas que atuam no setor de e-commerce. Muitos sistemas atuais enfrentam dificuldades relacionadas à escalabilidade, lentidão em períodos de pico, falhas na integração entre serviços e limitações na personalização da experiência do usuário. Além disso, consumidores esperam plataformas que ofereçam navegação fluida, segurança nas transações e suporte eficiente. O contexto tecnológico atual exige soluções que sejam capazes de lidar com grandes volumes de dados e acessos simultâneos, o que torna essencial o uso de arquiteturas distribuídas. O projeto será desenvolvido considerando esse cenário, com foco em empresas que comercializam eletrônicos e buscam modernizar sua infraestrutura digital.

## Objetivos

Objetivo Geral:
Desenvolver um software de e-commerce escalável com arquitetura de sistema distribuído, voltado para o setor de tecnologia, que ofereça alta disponibilidade, escalabilidade e uma experiência de usuário otimizada, servindo de alternativa ao modelo de marketplace irrestrito adotado por grandes grupos do varejo.

Objetivos Específicos:
- Propor um modelo de catálogo de serviços que mantenha o foco no público-alvo;
- Definir requisitos técnicos iniciais para escalabilidade, segurança e confiança do consumidor;
- Desenvolver uma aplicação Web;
- Desenvolver uma aplicação Mobile;
- Implementar uma arquitetura baseada em microserviços para garantir modularidade e facilidade de manutenção;
- Pesquisar e propor soluções reais para que se atinja o requisito da disponibilidade do sistema.

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
|RNF-002| O tempo de resposta da aplicação deve ser de, no mínimo, 100ms. |  MÉDIA | 
|RNF-003| A aplicação deve ser disponibilizada tanto para web quanto para mobile.  |  ALTA | 
|RNF-004| A aplicação deve ser segura, usando boas práticas de segurança, atendendo à OWASP TOP03 2021 |  ALTA | 
|RNF-005| A aplicação deve ser escalável de maneira que possa atender eventuais picos e se adaptar a um constante crescimento de seus usuários. |  MÉDIA | 
|RNF-006| A aplicação deve ter um uptime de 95% ao ano.  |  MÉDIA | 
|RNF-007| A aplicação deve ser de fácil manutenção tanto para corrigir erros quanto para extender suas funcionalidades. |  MÉDIA | 

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |


# Catálogo de Serviços

Nosso e-commerce oferece um conjunto de funcionalidades que garantem praticidade, segurança e uma boa experiência para clientes e administradores.

---

##  Cadastro e Login
- Criação de conta de forma simples e segura.  
- Acesso ao sistema com login e senha.  
- Perfil personalizado com dados.  

---

##  Catálogo de Produtos
- Vitrine completa com descrição, preço, fotos e estoque.  
- Filtros de busca por categoria.  
- Navegação intuitiva para facilitar a experiência de compra.  

---

##  Carrinho de Compras
- Adição e remoção de itens de forma prática.  
- Atualização de quantidades conforme a necessidade.  
- Itens salvos no carrinho mesmo após sair da conta (usuários logados).  

---

##  Pedidos  
- Acompanhamento do status do pedido (pendente, pago, enviado e entregue).  
- Histórico completo de pedidos anteriores.  

---

##  Administração (para gestores)
- Gerenciamento de produtos, preços e estoque.  
- Acompanhamento de pedidos e clientes em tempo real.  
- Relatórios de vendas e dados estratégicos para o negócio.  

## Observações Técnicas
- **Deploy automático:** a cada push no GitHub, a Vercel realiza o deploy contínuo da aplicação.
- **Serverless:** não há acesso direto a servidores ou containers; escalabilidade e disponibilidade são gerenciadas pela plataforma.
- **Variáveis de ambiente:** configuradas diretamente na Vercel, garantindo segurança das credenciais e integrações.


# Arquitetura da Solução

Arquitetura é organizada, à nível de UI, com serviço de hospedagem de arquivos estáticos com Vercel. APIs organizadas em diferentes micro serviços hospedadas em uma máquina virtual com Docker. Nginx como o gateway das requisições que os usuários farão e o Supabase como provedor de banco de dados. 
![arquitetura (1)](https://github.com/user-attachments/assets/e5540ced-0d10-4e87-9483-47a9689b674a)

## Tecnologias Utilizadas

### Diagrama da stack proposta:

![stack_proj_pucminas_6 (3)](https://github.com/user-attachments/assets/b44d6572-f319-498b-8e74-3ac8b5d06480)

### Descrição da stack e do desenvolvimento:

No front-end intentasse utilizar React com ou sem o uso de ferramentas como TailwindCSS, Material UI ou Bootstrap com a intenção de trazer maior padronização e produtividade no desenvolvimento. Na parte mobile objetivasse desenvolver a aplicação com React Native dada a popularidade e a maturidade desse framework. Em ambas as aplicações de UI Web e de UI Mobile o objetivo é usar a língua de programação TypeScript pela grande integração com a runtime Node.js (fundamental para React e React Native) e pela resiliência à erros com o apoio da forte tipagem oferecida. Quanto ao desenvolvimento das APIs que serão chamadas pelas aplicações de UI intentasse usar C# com o apoio do framework .NET usando Swagger como ferramenta de documentação e padronização. Na camada de persistência usar Supabase que na prática significará, para o desenvolvimento, um banco de dados relacional dentro dos padrões do PostgreSQL.

Quanto ao deploy o serviço de aplicações estáticas como o UI será feito com o Vercel, já as APIs com Docker em máquinas virtuais e o banco administrado via Supabase.

O desenvolvimento poderá ser feito com o apoio da IDE de preferência do desenvolvedor, sendo crucial, no contexto das APIs que apoiam o UI, ter disciplina em desenvolver e testar a execução das aplicações em formato containerizado padrão utilizando Docker para evitar questões de compatibilidade.

Quanto ao fluxo de desenvolvimento há o objetivo de separar cada serviço em diferentes repositórios no GitHub seguindo o padrão Conventional Commits nas mensagens de commit, a criação de forks indivuais, a criação de pull requests e a revisão para o merge. Fluxo importante para garantir um histórico claro e saudável das contribuições feitas por cada desenvolvedor, evitar bugs e integrar todo o time de desenvolvimento nas atividades sendo feitas pelos colegas com as revisões, e, por fim, evitar a perda de rastreabilidade de contribuições que apresentem erros ao longo do ciclo de vida do software. 

### Jornada do usuário:

Quando o usuário acessa o domínio da TeraBum, o serviço de hospedagem do Vercel serve o UI ao passo que esse UI é carregado no navegador do usuários requisições são disparadas para a API de vitrine servir eventuais sugestões e produtos que devem já aparecer para o usuário. Caso precise fazer um login, busca ou começar a adicionar itens no carrinho os micro serviços relacionados também serão chamados pela UI servindo o necessário. Com essas interações o banco de dados do e-commerce irá atualizar com históricos de busca, compras, cadastros etc.

## Hospedagem

A hospedagem da aplicação foi realizada na plataforma Vercel, escolhida por sua integração nativa com projetos desenvolvidos em Next.js e por oferecer um ambiente serverless com escalabilidade automática, simplificando o processo de deploy e manutenção.

O fluxo de hospedagem ocorre da seguinte forma:

- O código-fonte da aplicação é versionado em um repositório no GitHub.

- O repositório é integrado diretamente à Vercel, permitindo que a cada novo push seja gerado automaticamente um novo deploy.

- Variáveis de ambiente (como chaves de API e credenciais de banco de dados, ex.: Supabase), são definidas no painel da Vercel, garantindo segurança e isolamento de informações sensíveis.

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

### Semana 4

Atualizado em: 31/08/2025

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Lucas e Daniela | Introdução   | 24/08/2025     | 31/08/2025 | ✔️    | 31/08/2025    |
| Lucas e Daniela | Objetivos    | 24/08/2025    | 31/08/2025 | ✔️    | 31/08/2025     |
| Lucas e Daniela | Problemas  | 24/08/2025    | 31/08/2025 | ✔️     |   31/08/2025    |
| Lucas e Daniela | Justificativa  | 24/08/2025    | 31/08/2025 | ✔️     |   31/08/2025    |
| Lucas e Daniela | Público-Alvo  | 24/08/2025    | 31/08/2025 | ✔️     |   31/08/2025    |
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
