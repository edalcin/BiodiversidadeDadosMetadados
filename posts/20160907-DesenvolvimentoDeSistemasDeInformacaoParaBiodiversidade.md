# Desenvolvimento de sistemas de informação para biodiversidade - armadilhas e variáveis de sucesso

## 07 de Setembro de 2016

>"Most software today is very much like an Egyptian pyramid with millions of bricks piled on top of each other, with no structural integrity, but just done by brute force and thousands of slaves."
>
>Alan Kay

O desenvolvimento de sistemas de informação para biodiversidade não é trivial. Na verdade, o domínio da biodiversidade agrega um complicador - a "diversidade biológica" - a algo que já é, em si, complexo: materializar o desejo do usuário na forma de um software. Neste contexto, o volume de frustração gerado é, via de regra, superior ao volume de satisfação obtido.

Não é de hoje que computadores são utilizados para manejar dados de biodiversidade. Na década de 60 e 70, já eram utilizados para processar registros de herbários e na década de 80 muito se avançou na gestão de dados taxonômicos, ou sobre as espécies. Entretanto, mesmo com todo este conhecimento acumulado, uma grande maioria de iniciativas louváveis pereceram, enquanto outras poucas sobreviveram. Assim, o que pretendo ponderar aqui é porquê algumas iniciativas em sistemas de informação sobre biodiversidade falham enquanto outras são bem sucedidas. Acredito que exista algum aprendizado nesta reflexão.

Nesta análise, não tenho como deixar de considerar um artigo que escrevi em 1998, que este ano completa a maioridade, intitulado "[Aspectos na Implementação de Sistemas de Registros Informatizados em Jardins Botânicos](https://www.researchgate.net/publication/265325233_Aspectos_na_Implementacao_de_Sistemas_de_Registros_Informatizados_em_Jardins_Botanicos)" [1]. É curioso perceber que, apesar da idade, as considerações ali contidas ainda são válidas, obviamente respeitando-se as diferenças do cenário tecnológico vigentes na época.

O artigo citava "armadilhas" a se evitar e "passos fundamentais para o sucesso" na implementação de um "sistema de registros informatizado". Seguirei nesta linha, buscando validar, atualizar ou complementar estes pontos, procurando encontrar um cenário propício para o desenvolvimento de sistemas de informação sobre biodiversidade bem sucedidos.

## Armadilhas

### Investimento vs. custeio

Muitos sistemas de informação sobre biodiversidade foram e são desenvolvidos tendo como fonte de recursos "projetos" que, por definição, são efêmeros. Ao final do projeto, o que resta é uma herança financeira e operacional que muitas vezes ultrapassa os custos iniciais de desenvolvimento.

![Ponta do Iceberg](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/tip-of-the-iceberg.jpg)

Até recentemente era quase "moda" as propostas de projetos de pesquisa conterem como "objetivo" ou "resultado esperado" um "banco de dados" (seja lá o que isso fosse!). Projetos individuais geralmente consideravam que uma planilha Excel já cumpria a promessa feita na proposta, e o sujeito entregava um "CD" gravado com a planilha junto com o relatório final do projeto e dormia o sono dos justos.

Projetos institucionais vultosos ou de redes de pesquisa, entretanto, eram e são bem mais ambiciosos e poucos foram os que conseguiram, não só prever, mas lidar com esta herança financeira e operacional ao final do projeto (mais precisamente, do financiamento).

Dependendo do sistema de informações, o custo se propaga de forma assustadora pela infraestrutura de TI da instituição - armazenamento, processamento e conectividade - como é o caso, por exemplo, de herbários virtuais que associam aos dados as imagens das exsicatas em alta resolução, gerando um custo significativo de armazenagem com alta disponibilidade e backup.

Em essência, a armadilha aqui é considerar apenas os custos de desenvolvimento em si, sem considerar os custos de gestão do conteúdo e a manutenção do sistema e da infraestrutura que o mantém, como fixos, recorrentes e eternos.

A reinvenção da roda

Outra armadilha muito comum é a postura de alguns desenvolvedores em ignorar todo o conhecimento já gerado em torno do tema, e desenvolver um modelo lógico do sistema com base apenas na sua percepção do problema.

Profissionais de Tecnologia da Informação aprendem na universidade algumas "receitas de bolo". Controle de estoque, contabilidade e recursos humanos são alguns exemplos de sistemas que são usados como exercícios na formação destes profissionais e alguns resolvem extrapolar nas analogias quando confrontados com o domínio da biodiversidade. Certa vez um destes profissionais chegou a conclusão de que um sistema para herbários nada mais era que um sistema "para bibliotecas". Pensei com meus botões que nunca havia visto uma biblioteca onde os livros ficavam mudando o título e o autor...

O que tenho visto é que no processo de concepção do sistema, onde o entendimento dos problemas que se quer resolver (domínio do problema) interage com a equipe técnica de sistemas (domínio da solução), a falta do profissional que trafegue com conhecimento e desenvoltura pelos dois domínios acaba levando a equipe técnica de sistemas a desenvolver um modelo sem considerar soluções já existentes e "reinventar a roda".

Esta armadilha é muito comum em iniciativas que, por diversas razões, contratam no mercado uma empresa especializada em desenvolvimento de sistemas. Nestas empresas é razoável encontrar equipe técnica capacitada a desenvolver sistemas mais "tradicionais", sem conhecimento prévio ou experiência com o domínio do problema - a biodiversidade.

De qualquer forma, ignorar conceitos e modelos propostos [2, 3 e 4] e o esforço intelectual já sistematizado de muitos [5], é uma armadilha a se evitar.

Qualidade do sistema vs. qualidade do conteúdo

Como diz uma querida amiga, "estudos indicam" [6] que, resumidamente, um sistema de informações de "sucesso" é resultado de uma relação entre um software de qualidade e um conteúdo de qualidade.

Parece óbvio mas desenvolver o sistema é apenas parte da empreitada. Preenchê-lo com dados de qualidade é um desafio e tanto. Em essência, é a qualidade da informação que o sistema é capaz de gerar ou apresentar que define a qualidade do todo.

Conheço algumas iniciativas que fracassaram ou, segundo a figura acima, não criaram o impacto esperado porque a qualidade dos dados que contém é muito baixa. Neste ponto, é importante perceber o peculiar dinamismo de um dos pilares dos sistemas de informação sobre biodiversidade que é a nomenclatura taxonômica. Desconsiderar a complexidade e dinamismo do backbone taxonômico, por exemplo, também pode ser uma receita para o fracasso.

Ainda neste aspecto - qualidade do conteúdo - muitos relutam em tornar público dados que consideram de baixa qualidade, com medo de sofrer do mal acima. Entretanto, o remédio para este mal é a responsividade do conteúdo em se atualizar com base nas críticas feitas. Oferecer um canal de comunicação com o usuário, e responder a sua crítica (quando pertinente) de forma rápida parece ser o segredo do sucesso.

Um exemplo que posso usar é o da Flora do Brasil 2020. Como qualquer base de dados neste universo, não é perfeita. Porém, absorve a crítica de cerca de 700 especialistas, através da sua interface, projetada para tal; e ainda conta com uma equipe de suporte e um e-mail de contato. O conteúdo da Flora do Brasil 2020 é produto de uma construção coletiva com alto dinamismo e o sistema foi pensado inicialmente desta forma[7]. Isso parece ter feito toda a diferença.

Em resumo, um sistema de informações com dados incapazes de responder à críticas, seja feita por contribuição de um especialista ou pela obviedade do fato (a ocorrência de uma árvore no meio do oceano), entra no ciclo acima de insatisfação do usuário, gerando uma baixa utilização do sistema.

Vale notar que a busca constante pela qualidade do conteúdo (dados) e daquilo que o contém (o sistema) faz parte da primeira "armadilha": a herança operacional.

Variáveis ambientais favoráveis

Gosto de cozinhar e na cozinha aprendemos que o que sai de lá para a mesa depende do que tem na geladeira, dos equipamentos disponíveis e do repertório de receitas e da criatividade do chef. Simples assim. E não é diferente no desenvolvimento de sistemas. Cada {grupo, instituição, empresa} tem um conjunto de "variáveis" que acaba por condicionar o desenvolvimento, deixando suas marcas no produto final. Algumas variáveis causam impacto negativo, como por exemplo a falta de comprometimento da alta direção [8, 9], mas vou me deter aqui no que considero variáveis ambientais favoráveis ao desenvolvimento de sistemas de sucesso.

Liberdade tecnológica

Preciso confessar que fui, em parte, motivado a escrever este texto por uma troca de emails recente com uma colega do South African National Biodiversity Institute - SANBI, que lamentava não ter um ambiente capaz de produzir um sistema de avaliação de risco de extinção como o do Centro Nacional de Conservação da Flora - CNCFlora.

Na conversa, ficou claro as diferentes "variáveis ambientais" que as duas instituições possuíam e uma delas era restrição a determinadas plataformas (ou obrigatoriedade de ficar restrito a outras):

...According to our Biodiversity Informatics Manager they do not want us to develop any system that requires use of open source software. He only wants us to use MySQL or Microsoft applications...

Existem muitas definições para um termo novo que anda frequentando sites de desenvolvimento: "Agnosticismo Tecnológico". A que eu considero que melhor se aplica aqui é "Technology agnostic is a term that we use in the business that simply means, we are unbiased towards the use of different technology tools to solve different problems."

A essência desta variável que chamo aqui de liberdade tecnológica é oferecer aos arquitetos do sistema encontrar a melhor solução tecnológica para o problema, sem restrições.

É claro que, como em tudo, a liberdade absoluta é uma utopia e não seria razoável, por exemplo, que em nome desta "liberdade" se decidisse desenvolver um sistema em uma linguagem de programação obscura ou de baixa popularidade, pois sua manutenção estaria comprometida pela dificuldade de se encontrar recursos humanos no mercado.

Contudo, não me parece razoável também, como no caso do SANBI, restringir as opções de solução a um conjunto extremamente limitado de plataformas. É como ter na cozinha apenas batatas...

O exercício da liberdade tecnológica, em um ambiente receptivo, favorece a experimentação e a inovação. Como falado acima, desenvolver sistemas para biodiversidade não é trivial e não seria na trivialidade que encontraríamos as melhores soluções computacionais. Algumas novas tecnologias e abordagens parecem muito promissoras para lidar com dados de biodiversidade e especialmente com entidades biológicas, como bancos de dados orientados a grafos, para lidar com a complexa relação taxonômica e o conceito de taxon; bancos de dados NoSQL, para se libertar de esquemas rígidos de normalização; persistência e programação poliglota, buscando encontrar a melhor solução para cada problema; e arquitetura baseada em micro-serviços, potencializando a modularização e a reutilização de códigos.

Liberdade metodológica

Em fevereiro de 2001 dezessete desenvolvedores publicaram um manifesto que, ao meu ver, revolucionou a forma de se desenvolver software: o "Manifesto para Desenvolvimento Ágil de Software". O "Manifesto Ágil" possui um conjunto de 12 princípios que viraram de cabeça pra baixo as abordagens clássicas de desenvolvimento e suas métricas, e tiraram da zona de conforto os analistas "da velha guarda". Apesar de alguns métodos e práticas já existirem antes da publicação do manifesto, estes acabaram por se consolidar em torno do "movimento ágil", criando uma nova geração de desenvolvedores. Essa garotada rebelde, que não liga pra documentação, pontos de função nem pra especificação de requerimentos, praticamente nasceu com um mouse na mão e, por isso, merece respeito. Além de respeito, se tiverem liberdade de usar métodos e práticas "ágeis", a chance de sucesso é muito grande.

Até pouco tempo, era difícil convencer os "Velhos Barões da TI" que estes novos métodos eram aceitáveis. Afinal, a ignorância é a irmã mais velha do medo. Contudo, felizmente, a Secretaria de Logística e Tecnologia da Informação do Ministério do Planejamento, Orçamento e Gestão lançou em 2015 o Guia de Projetos de Software com Práticas de Métodos Ágeis para o SISP! Minha fé na raça humana se renovou! Dá licença que escorreu uma lágrima aqui.... :)

Equipe técnica

Todos os projetos bem sucedidos que conheço tem a marca de alguém. Geralmente um desenvolvedor engajado e compromissado, quase um "lobo solitário", que leva o sistema nas costas usando de todas as habilidades técnicas que possui. Não vou citar nomes aqui mas, no Brasil e no exterior, conheço uma penca de pessoas que são imediatamente associadas à sistemas de informação em Biodiversidade. Desta forma, acredito que a primeira variável de sucesso relacionada à equipe técnica é uma equipe (ou mesmo "monoquipe") absolutamente compromissada com o sistema. A conclusão lógica imediata é que você só encontrara isso em uma equipe oferecida por uma empresa que visa lucro "por de um milagre divino"! Não quero generalizar aqui e cometer injustiças, até porque, como dizia Carl Sagan, "a ausência de evidência não é evidência da ausência". Pode até ser que aconteça alguém de uma equipe contratada e temporária crie uma relação forte com o sistema. Mas aquela relação quase que paternal, ou maternal, que já vi em alguns desenvolvedores, eu nunca presenciei em equipes contratadas de empresas. Cabe notar que, já presenciei projetos com rotatividade dos codificadores, mas com um compromisso enorme do "líder do projeto".

Também parece ser óbvio que nenhum excelente projeto ou modelo consegue resistir a uma equipe de desenvolvimento medíocre. Até para exercer as liberdades acima, é necessário uma "mente aberta" para o novo, uma receptividade para sair da zona de conforto tecnológica e metodológica, e pensar "fora da casinha". Um bônus espetacular é contar com uma equipe com um repertório tecnológico e metodológico já considerável.

Por fim, como falei lá em cima na "reinvenção da roda", a existência de um profissional na equipe, que consiga estabelecer uma ponte entre os especialistas em biodiversidade (domínio do problema) e os especialistas em TI (domínio da solução), é absolutamente fundamental. A maioria dos "lobos solitários" que citei acima eram, e são, verdadeiros camaleões. Para quem não tem conhecimento prévio, é impossível dizer qual a formação do sujeito, tamanha sua desenvoltura nas duas áreas. Entretanto, a história conta que, na época pré-internet, a maioria dos "grandes" sistemas para biodiversidade foram desenvolvidos por biólogos que se interessaram por TI. Hoje acho que é "pau-a-pau"!

Cumplicidade com os usuários

Acima, em "Qualidade do Sistema vs. Qualidade do Conteúdo", comentei da importância de se ter um canal de comunicação com os usuários no sentido destes poderem contribuir com a qualidade do conteúdo. Entretanto, o mesmo vale para a qualidade do sistema. É importante que os usuários se sintam a vontade, e tenham os meios, para apontar "bugs", criticar e sugerir mudanças no sistema, não de forma eventual - geralmente solicitada algumas semanas ou dias antes do "lançamento oficial" do sistema, mas de forma constante e permanente.

O usuário deve se sentir parte integrante do processo de construção e aprimoramento do sistema. Da mesma forma, canais claros, simples e eficientes devem ser criados para uma comunicação fluida entre os usuários e o líder da equipe de desenvolvimento. As metodologias de se estabelecer prioridades de ajustes no sistema devem ser estabelecidas em conjunto com os usuários. Os "custos" (complexidade) e impactos das sugestões dos usuários também devem ser compartilhados, para que estes entendam que um pedido que parece "simples", requer um esforço monumental e dias de trabalho reescrevendo códigos. Feedbacks devem SEMPRE ser dados, preferencialmente com prazos.

Em suma, os usuários devem se sentir parte, não só integrante mas fundamental, do interminável processo de desenvolvimento do sistema, discutindo as prioridades custos e impactos junto com a equipe de desenvolvimento, e ciente das limitações e dificuldades.

"O diabo mora nos detalhes"

Por fim, alguns detalhes que podem fazer a diferença:

Exportação e exposição dos dados

Vivemos em uma época em que máquinas conversam com máquinas. Além disto, dados sobre biodiversidade querem e precisam ser abertos e integrados [10, 11, 12]. Seja para pesquisadores que querem usar os dados em processos de análise e síntese, seja para agregadores, como SiBBr, Portal da Biodiversidade do ICMBio ou GBIF, exponha os dados do seu sistema. Faça isso tanto para máquinas como para humanos, usando padrões internacionais de dados e metadados e na maior variedade de formatos possível. DWC, EML, XLS, JSON, XML, DBF, CSV, PDF, DOC, SHP, ODS e SQL são alguns dos sabores que você pode e deve oferecer seus dados. Afinal, "o cliente tem sempre razão"!

Agora, vamos todos dar as mãos e recitar o "mantra" das "Três Leis dos Dados Abertos Governamentais", mas não exclusivas à estes, propostas por David Eaves e abençoadas pelo governo brasileiro:

Se o dado não pode ser encontrado e indexado na Web, ele não existe;
Se não estiver aberto e disponível em formato compreensível por máquina, ele não pode ser reaproveitado; e
Se algum dispositivo legal não permitir sua replicação, ele não é útil.

AMÉM!

Licença de uso

Esteja certo de que seus dados são oferecidos acompanhadas de uma licença de uso. Fica muito mais fácil e atrativo usar seus dados quando os termos para usá-los são claros e explícitos. Existem várias licenças disponíveis e o GBIF possui documentos [13] e orientações sobre isso. Contudo, se for possível exercitar o desapego na sua forma mais sublime, opte pela Creative Commons Zero (CC0). Aqui está uma boa justificativa para optar pela CC0.

Valorize as críticas ao conteúdo

A Internet criou bilhões de juízes cheios de razão e pedras na mão para criticar seu sistema e seus dados. Enquanto alguns deles querem apenas fazer você ficar chorando na cama em posição fetal, outros estão realmente dispostos a colaborar. Aproveite isso! Crie um canal de comunicação eficiente e SEMPRE dê um feedback para uma colaboração. Preferencialmente, pense no seu sistema como uma plataforma colaborativa [7, 14].

Métricas de acesso

Procure medir o acesso ao seu sistema. "Quem", "quando", "como", "de onde", "com o quê", "vindo de onde", "procurando o quê" são algumas das perguntas que ajudam no ajuste fino do seu sistema e do conteúdo e, acima de tudo, dá uma visão do impacto que ele pode estar causando. O volume de acesso qualificado ainda é um argumento irrefutável na busca por recursos para a evolução ou manutenção do seu sistema.

Design "responsivo"

A explosão dos dispositivos móveis com acesso a internet criou uma demanda para os web designers que é fazer com que um site "caiba", de forma bela e elegante, em uma tela de proporções e orientações variadas. Surgiu então o "Web Design responsivo", cuja essência se resume a ilustração da Stéphanie Walter ai em baixo: "conteúdo é como água".

Um sistema baseado na web deve considerar ser acessado não só por computadores desktop mas por dispositivos móveis também. Desta forma, sistemas que se ajustam elegantemente à estes dispositivos ganham uma estrelinha dourada!

Referências

[1] Dalcin, E. (1988). Aspectos na Implementação de Sistemas de Registros Informatizados em Jardins Botânicos. Plumeria, Boletín de los jardines botánicos de Latinoámerica y del Caribe, No.6. ISSN- 1405-6593. Associación Latinoamericana y del Caribe de Jardines Botanicos.

[2] Berendsohn, W. G. (1995). The concept of "potential taxa" in databases. Taxon 44: 207-212. . ISSN 0040-0262.

[3] Berendsohn, W. G., et al. 1999. A comprehensive reference model for biological collections and surveys. Taxon (1999): 511-562.

[4] Common Data Model. EDIT Platform for Cybertaxonom, n.d. Web. 30 Aug. 2016.

[5] Hobern, Donald, et al. (2013). Global biodiversity informatics outlook: delivering biodiversity knowledge in the information age. Global Biodiversity Information Facility (Secretariat).

[6] DeLone, W. H., & McLean, E. R. (1992). Information systems success: The quest for the dependent variable. Information systems research, 3(1), 60-95.

[7] Esteves, M. G. P., Zimbrão, G., do Carmo, F. B., Forzza, R. C., Vaz, M., Filardi, F. L. R., ... & de Souza, J. M. (2015, May). A crowdsourcing approach to the design of Virtual Research Environments. In Computer Supported Cooperative Work in Design (CSCWD), 2015 IEEE 19th International Conference on (pp. 455-461). IEEE.

[8] de Jesus, R. G., & de Araujo, P. M. C. (2011). O Impacto do Compromentimento na Implantação de Sistemas de Informação: o Caso Garoto-sap. VIII Simpósio deExcelência em Gestão e Tecnologia.

[9] Ferreira, A. C. de Sousa & Bufoni, A. L. (2006). Fatores de sucesso e insucesso na implementação de sistemas de informação gerencial: estudo do caso do segmento de exploração e produção de petróleo da Petrobrás S/A. Revista de Administração Contemporânea, 10(2), 9-31. <https://dx.doi.org/10.1590/S1415-65552006000200002>

[10] Costello, M. J., Michener, W. K., Gahegan, M., Zhang, Z. Q., & Bourne, P. E. (2013). Biodiversity data should be published, cited, and peer reviewed. Trends in Ecology & Evolution, 28(8), 454-461.

[11] Sayão, L. F., & Sales, L. F. (2014). Dados abertos de pesquisa: ampliando os conceitos de acesso livre. RECIIS–Rev. Eletron. de Comun. Inf. Inov. Saúde, 8(2), 76-92.

[12] Uhlir, P. F., & Schröder, P. (2007). Open data for global science. Data Science Journal, 6, OD36-OD53.

[13] Chavan, V. (2012). Recommended Practices for Citation of the Data Published through the GBIF Network. Copenhagen: GBIF Secretariat. Retrieved July, 30, 2013.

[14] Johnson-Lenz, Peter, and Trudy Johnson-Lenz. Rhythms, Boundaries, and Containers: Creative Dynamics of Asynchronous Group Life. N.p., Apr. 1990. Web. 7 Sept. 2016.
