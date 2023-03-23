# Sustentabilidade de Sistemas de Informação para Biodiversidade
## 15 de Janeiro de 207

O Blog do rOpenSci trouxe um artigo bem interessante do Daniel Katz cujo primeiro parágrafo traz uma pergunta que não quer calar:

>“A research (software) project often starts with a bright idea and an initial commitment of volunteer time, or perhaps, a fixed term grant. But what happens after that initial activity? How can the project continue to sustain itself?”

Este é o “leão que tenho de matar” todos os dias há mais de 25 anos, quando desenvolvi meu primeiro sistema “sério” e, hoje em dia, envolvido com o desenvolvimento e manutenção dos sistemas institucionais do Instituto de Pesquisas Jardim Botânico do Rio de Janeiro. Além disso, já havia comentado sobre essa “armadilha” no texto “Desenvolvimento de sistemas de informação para biodiversidade“, publicado aqui anteriormente.

O fato é que, conforme o iluminado parágrafo proferido pelo Dr. Katz acima, estamos desenvolvendo sistemas em nossas instituições para lidar com as demandas por informação que, com raríssimas exceções (se é que existem), são sistemas que foram iniciados com recursos de projetos, contratando {empresas, bolsistas, fábricas de software, fundações etc.} . Por definição, projetos são finitos, assim como seus recursos. Porém, paradoxalmente, o sistema que foi desenvolvido como foco ou suporte para um determinado projeto é (ou deveria ser) perene.

Aqui é preciso deixar claro a diferença entre “software para pesquisa” e “software de infraestrutura”. O software para pesquisa é uma ferramenta que o pesquisador usa para manipular, processar e analisar os dados que coletou. Esta é uma ferramenta de uso imediato que pode ser arquivada com os dados da pesquisa para garantir a reprodutibilidade dos resultados.

O “software de infraestrutura” é aquele que serve a uma comunidade de pesquisadores e compõe uma rede de recursos interconectados – a chamada “Cyberinfrastructure“, definida desta forma:

>“Cyberinfrastructure consists of computing systems, data storage systems, advanced instruments and data repositories, visualization environments, and people, all linked together by software and high performance networks to improve research productivity and enable breakthroughs not otherwise possible.“[1]

Apesar da importância de ambos para a ciência, meu foco aqui será para os sistemas de infraestrutura pois, por uma questão de escala, representam um problema de sustentabilidade bem maior. Mais precisamente, em sistemas de informação sobre biodiversidade.

Outro ponto que precisamos deixar claro aqui é o que significa “sustentabilidade” para um software. Vou “roubar” a definição do Dr. Katz (que tem a sensação que também roubou de alguém…) que diz:

>“Software is sustainable if it will continue to be available in the future, on new platforms, and meeting new needs.“

## Cenário

Não é demais lembrar de alguns pontos:

* Software é essencial para quase a totalidade da ciência hoje. Ele está entre os dados e os resultados;
* Desenvolvimento e manutenção de software é dependente de recursos humanos capacitados escassos e, consequentemente, caros;
* Desenvolvimento e manutenção de software é dependente de infraestrutura computacional compatível;
* Desenvolver um software e não manter, é como plantar e não regar. Simples assim.

O artigo do Dr. Katz aponta para uma lista, originalmente criada por Nadia Eghbal e adaptada (“forked”) por ele, contendo formas de financiamento de projetos de software para pesquisa que é bem interessante e inspiradora. Porém, algumas das estratégias listadas ali, creio eu,  tem limitações para serem aplicadas à sistemas de informação componentes de uma infraestrutura nacional, na grande maioria dos casos desenvolvidos e mantidos por instituições do governo federal.

Entretanto, tenho amadurecido e discutido com alguns pares uma visão que é na verdade uma composição de várias estratégias de financiamento ali citadas, que gostaria de compartilhar com vocês aqui.

## Desenvolvimento Colaborativo

Desenvolvimento colaborativo, ou “Commons-based peer production” não é novidade, e o seu produto mais conhecido é o Linux. Entretanto, a visão que venho amadurecendo é de um “quadro de avisos” público na Internet onde necessidades de desenvolvimento são “postadas” para que desenvolvedores possam selecionar, desenvolver e entregar. Muito parecido também com um “Sprint Backlog” do SCRUM. No entanto, a diferença desta proposta é que ela envolve um modelo de negócio bem claro, baseado na técnica do “Gamification“.

Funciona da seguinte forma: demandadores de códigos postam suas necessidades no quadro de avisos, que programadores autônomos podem pegar e desenvolver de forma voluntária. A cada entrega destas tarefas mais simples e desenvolvidas de forma gratuita, o programador vai acumulando “pontos” que irão permitir acessar tarefas mais complexas do quadro de avisos, estas então pagas, financiadas por patrocinadores.

<img src="http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/sustentabilidadeSistemas1.jpg" width="200">

Assim, o quadro de avisos seria uma mistura de tarefas simples e gratuitas, abertas para todos os programadores que quisessem contribuir; e de tarefas mais complexas pagas, acessível apenas aos programadores que desenvolveram e entregaram, com qualidade, um conjunto de tarefas gratuitas.

Programadores iriam evoluindo e ganhando “reputação” através do sistema de pontuação e avaliação dos contratantes, acessando tarefas cada vez mais complexas e mais bem remuneradas.

Contratantes teriam então acesso à um conjunto de desenvolvedores maior, mais dinâmico, avaliados e certificados pelo conjunto de suas entregas, podendo ter acesso à componentes do seu sistema com orçamento muito baixo.

Não é demais notar que contratar desenvolvedores online não é nenhuma novidade, e diversos sites estão ai oferecendo programadores, até na Índia. Aliás, Indianos seriam muito bem vindos à frequentar o “quadro de avisos”, assim como programadores de qualquer nacionalidade e qualquer parte do globo, visto que linguagens de programação são “Língua Franca“.

## Premissas

Obviamente, algumas premissas são fundamentais para este sistema funcionar e o verdadeiro pilar que sustenta esta proposta é a arquitetura orientada a Microserviços [2].

Abandonar o desenvolvimento de sistemas “monolíticos” em prol dos sistemas modulares baseados e arquitetura de microserviços, por si só, já traria enormes benefícios[3] mas, acima de tudo, permitiria que pudéssemos otimizar os parcos recursos para o desenvolvimento de sistemas, compartilhando e re-utilizando “pedaços” de sistemas que são comuns aos sistemas de informação sobre biodiversidade. Acessar um “backbone” taxonômico, por exemplo.

Não vejo porquê precisamos ficar duplicando esforços desenvolvendo as mesmas funcionalidades para sistemas que tem uma sobreposição enorme destas funcionalidades. Na prática, um desperdício de dinheiro público.

Reconheço que o desafio é monumental, pois envolve  uma mudança cultural significativa, mas  acredito que o esforço não só vale a pena como pode ser atingido em etapas simples e de forma gradual.

Assim, o primeiro passo seria criar um espaço que pudesse agregar programadores com interesse, capacidade e competência para desenvolver sistemas de informação para a biodiversidade e conservação, e onde potencias contratantes pudessem encontrá-los e selecioná-los com base em suas competências. Este espaço, embrião da proposta descrita acima, seria um espaço voltado para estes programadores trocarem idéias e ter acesso à notícias relevantes e de oportunidades de trabalho.

Uma proposta nesta direção é a do "Coders for Conservation". Um passo para um longo caminho: identificar, valorizar e promover a formação de programadores voltados para biodiversidade e conservação. Um recurso fundamental para fazer avançar a ciência, possibilitando transformar o dado em informação.

> :warning: __Atualização__: A proposta do "Coders for Conservation" não "decolou" e foi descontinuada.

## Referências

[1] Stewart, Craig A., et al. “What is cyberinfrastructure.” Proceedings of the 38th annual ACM SIGUCCS fall conference: navigation and discovery. ACM, 2010.

[2] Fowler, Martin, and J. Lewis. “Microservices a definition of this new architectural term.” URL: http://martinfowler. com/articles/microservices. html. Acessado em 15/01/2017.

[3] Dragoni, Nicola, et al. “Microservices: yesterday, today, and tomorrow.” arXiv preprint arXiv:1606.04036 (2016).

