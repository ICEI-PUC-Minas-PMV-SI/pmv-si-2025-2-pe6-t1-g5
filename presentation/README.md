# Apresentação da Solução

## O Processo de Desenvolvimento do TeraBum, um e-commerce de tecnologia
O desenvolvimento do projeto ocorreu de forma progressiva e estruturada, iniciando-se pelo estudo detalhado do contexto do problema. Analisamos a demanda crescente por e-commerces de eletrônicos eficientes, modernos e com boa experiência de compra, o que nos permitiu definir a motivação, o problema central, os objetivos gerais e específicos, o público-alvo e a justificativa. Também levantamos os requisitos funcionais e não funcionais, organizamos o catálogo de serviços e estabelecemos a arquitetura, tecnologias e forma de hospedagem. Nessa etapa, consolidamos toda a base conceitual do sistema — o que seria construído, para quem seria feito e quais regras e limitações deveriam ser atendidas.

Com o contexto definido, avançamos para a fase de desenvolvimento das APIs, onde modelamos as entidades do banco de dados, estruturamos os microserviços e definimos os endpoints necessários para o funcionamento da aplicação. Foram documentados os módulos de Produtos, Usuários, Pedidos, Carrinho, Catálogo e Estoque, assim como o fluxo de autenticação, integração com o backend e estratégias de versionamento. Também foi definida a arquitetura de comunicação entre serviços, a análise de infraestrutura inicial com Docker e API Gateway, e a implementação do banco de dados no Supabase.

Em seguida, iniciamos o desenvolvimento do frontend Web, onde foram construídas as telas de acordo com os requisitos levantados: página inicial com listagem de produtos, detalhes do produto, sistema de busca, carrinho, autenticação e fluxo de compra. A aplicação foi integrada com a API, configuramos o deploy contínuo e realizamos testes de navegação, ajustes de layout, componentização e melhorias de usabilidade.

Na última fase, desenvolvemos o aplicativo Mobile, mantendo a mesma lógica do frontend Web e consumindo as APIs já estruturadas. Foram implementadas as telas de autenticação, listagem de produtos, detalhes, carrinho e pedidos, garantindo fluidez de navegação e adaptação ao uso em smartphones. Também realizamos testes, validações de estados, ajustes de integração e otimizações específicas para dispositivos móveis.

## Avaliação dos Frameworks e Tecnologias Utilizadas
Durante o desenvolvimento, utilizamos diversas tecnologias que possibilitaram a criação de um ecossistema consistente:
- React e React Native: proporcionaram agilidade na construção das interfaces Web e Mobile, garantindo componentização e reaproveitamento de lógica.
- React Native Paper: facilitou a padronização visual e a construção de interfaces responsivas no mobile.
- Node.js + APIs REST: possibilitaram um backend modular em microserviços, com endpoints bem definidos e de fácil manutenção.
- Supabase (PostgreSQL): se mostrou uma solução eficiente para banco de dados, com boa modelagem, autenticação e integração simplificada.
- Docker: contribuiu para padronizar ambientes e facilitar a infraestrutura inicial.

No geral, os frameworks atenderam às necessidades do projeto, oferecendo boa performance e flexibilidade. Entretanto, algumas dificuldades foram observadas, como a curva de aprendizado inicial em React Native e desafios de integração entre serviços em casos específicos.

## Propostas de Melhoria da Arquitetura e do Processo
Com base na experiência prática, identificamos alguns pontos de melhoria:
- Padronização mais rígida dos padrões de código para garantir maior uniformidade entre os microserviços.
- Automatização de testes (unitários e de integração), que ainda foram pouco implementados na versão atual.
- Melhor organização dos serviços no backend, incluindo documentação de erros, códigos de status e padronização de mensagens.
- Implementação de logs estruturados e monitoramento mais robusto.
- Adoção de CI/CD completo no mobile, que foi menos automatizado que o Web.

Essas melhorias poderiam deixar o projeto ainda mais escalável, padronizado e preparado para evolução futura.

## Responsabilidades e Atribuições da Equipe

A divisão de responsabilidades ocorreu tanto no Web quanto no Mobile:

**Lucas Guedes**
- API: UserService
- Telas: Login e Autenticação
- Documentação e slides

**Daniela Assis**
- API: VitrineService
- Telas: Home, Busca e Detalhes do Produto
- Documentação, organização e suporte geral

**Tales Hein**
- APIs: EstoqueService, StockItems, StockMoves, Product, Warehouse
- Telas relacionadas ao Estoque
- Vídeo de apresentação

**João Gabriel**
- API: CartService
- Telas de Carrinho
- Vídeo de apresentação
- Forte participação na integração front–API

**Gabriel**
- API: OrderService
- Telas de Pedido e Pagamento
- Banco de dados no Supabase
- Destaque na comunicação entre front e backend

**Todos**
- Testes, revisão de código, integração com as APIs e contribuições gerais no GitHub.

Essa divisão clara permitiu que o projeto evoluísse de forma organizada e colaborativa, garantindo que cada membro contribuísse com partes significativas do sistema.

## Vídeo Demonstrativo Web
https://github.com/user-attachments/assets/c18c1455-6ce8-488f-a8c2-16072f21a519

## Vídeo Demonstrativo Mobile - Usuário Final
https://github.com/user-attachments/assets/bfde4918-7783-457f-81d1-b57c90510597

## Vídeo Demonstrativo Mobile - Administrador
https://github.com/user-attachments/assets/f8d38045-d5c4-4353-bcd3-78e1a6fb1787

