# Apresentação da Solução

Faça uma apresentação de um resumo de todos o processo de desenvolvimento e no final apresente a solução desenvolvida, usando um pequeno vídeo.

## O Processo de Desenvolvimento do TeraBum, um e-commerce de tecnologia
O projeto teve início com o estudo do contexto do problema, analisando a demanda crescente por e-commerces de eletrônicos eficientes, modernos e com boa experiência de compra. A partir dessa análise, definimos a motivação do projeto, o problema central, os objetivos gerais e específicos, assim como o público-alvo e a justificativa. Também levantamos os requisitos funcionais e não funcionais que iriam orientar o desenvolvimento, estruturamos o catálogo de serviços e definimos a arquitetura, tecnologias e forma de hospedagem. Nesse momento, organizamos toda a base conceitual do sistema — o que seria construído, para quem seria feito e quais regras e limitações ele deveria atender.

Consolidado o contexto, avançamos para a etapa das APIs, onde modelamos as entidades do banco de dados, estruturamos os microserviços e definimos os endpoints necessários para funcionamento do sistema. Nessa fase, foi documentado o papel de cada módulo (produtos, usuários, pedidos, carrinho, catálogo), assim como o fluxo de autenticação e integração com o backend. Também foram definidas as tecnologias utilizadas, a arquitetura de comunicação entre serviços, as estratégias de versionamento e a primeira visão funcional da infraestrutura, incluindo Docker, API Gateway e conexão com o banco. Essa etapa estabeleceu a base lógica do sistema e permitiu a criação dos serviços que dariam suporte às interfaces futuras.

Com a API estruturada, partimos para o desenvolvimento do frontend Web, criando a interface principal do e-commerce. Foram construídas as telas seguindo os requisitos levantados inicialmente: página inicial com listagem de produtos, visualização individual do item, carrinho, fluxo de compra e sistema de login/registro. A aplicação foi integrada com a API para consumo dos dados reais e configuramos o deploy contínuo, garantindo que atualizações fossem publicadas automaticamente. Essa fase também envolveu estilização, componentização, organização das rotas, testes de navegação e refinamentos de layout e usabilidade.

Por fim, a última etapa foi o desenvolvimento do aplicativo Mobile, trazendo a experiência do usuário para dispositivos móveis. A construção seguiu a mesma lógica do web, aproveitando a base da API e adaptando as telas para uma navegação fluida em smartphones. O app recebeu telas de autenticação, listagem de produtos, detalhes e carrinho, mantendo o foco em responsividade e experiência simplificada. Nessa fase também foram feitos ajustes de integração, testes, validação de estados e otimizações específicas para mobile.

Assim, o projeto evoluiu de forma sequencial: primeiro toda a estrutura teórica e contextual, depois o backend e APIs, em seguida o desenvolvimento do Web e por último o Mobile — resultando em uma solução completa, funcional e progressivamente construída.

## Vídeo Demonstrativo
