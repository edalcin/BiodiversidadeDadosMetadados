# A lâmpada e o abajur
## 09 de Dezembro de 2016

Quando vou falar de “padrões” com meus alunos ou em palestras, costumo dizer que “é muito bom poder ir comprar uma lâmpada sem precisar levar o abajur, pois o Parafuso de Edison é um padrão”.

É claro que o exemplo é apenas para efeito didático, visto que existem diferentes tamanhos de “Parafuso de Edison” (lilliput. miniatura, candelabro, pequeno, médio, gigante), e até outros padrões para se encaixar uma lâmpada em um soquete.

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/lampadaAbajur1.png)

Entretanto, ele é eficiente para ilustrar o o tema deste post, que é sobre o padrão de dados Darwin Core [1] e sua implementação – o Darwin Core Archive (DwC-A).

Mais precisamente, pretendo abordar aqui o papel deste padrão na integração de dados sobre biodiversidade, no escopo do projeto “National Strategy for Conservation of Threatened Species (PROSPECIES)“, caminhando para sua implementação pelo Ministério do Meio Ambiente (MMA), Instituto de Pesquisas Jardim Botânico do Rio de Janeiro (JBRJ), Instituto Chico Mendes de Conservação da Biodiversidade (ICMBio), e Instituto Brasileiro do Meio Ambiente e dos Recursos Naturais Renováveis (IBAMA).

## O Problema

>“_…Although the developments on this matter are improving over the past years, there is still need to further integrate existing databases; develop improved tools for managing, accessing and communicating credible data to support policy; update databases that are required by law; and build capacity to improve decision making processes and planning instruments…_”

O parágrafo acima identifica muito precisamente demandas claras e já identificadas previamente de integração de dados no âmbito do MMA e suas vinculadas e, no caso específico do projeto em questão, dados relacionados a espécies ameaçadas e sua conservação.

Corroborando, podemos citar SILVA et al., 2015 [2]: “A necessidade de integrar dados e gerar informações de qualidade para rápida tomada de decisão é fundamental para a implementação de estratégias efetivas de conservação da biodiversidade. Diversos temas relacionados a biodiversidade, como por exemplo, definição de áreas prioritárias para conservação ou elaboração de planos de ação para as espécies ameaçadas ou gestão de sistemas de áreas protegidas, necessitam de um grande esforço prévio de compilação de dados e qualificação da informação.”

O cenário institucional é composto por três instituições vinculadas ao MMA – JBRJ, ICMBio e IBAMA, que produzem ou tem sob sua guarda conjuntos de dados e informações fundamentais para tomada de decisão e formulação de políticas publicas em conservação da biodiversidade, e a integração destes conjuntos de dados heterogêneos e distribuídos requer, entre outras coisas, um padrão.

## Uma proposta de solução

Vários aspectos deste cenário e propostas de solução estão presentes no documento “Diretrizes para Integração de Dados de Biodiversidade” [2] publicado pelo próprio MMA em 2015, que traz, inclusive, uma “visão geral do sistema de informação para integração de dados do MMA” (Figura 1).

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/lampadaAbajur2.png)
_FIGURA 1 – Fonte: Silva et al. 2015_

Sem dúvida, concordo com os autores que precisamos estabelecer no âmbito do MMA e suas vinculadas uma Infraestrutura de Dados sobre Biodiversidade, numa escala ministerial do que havia sido discutido na proposta da INDBio. Contudo, quero focar aqui apenas em um detalhe desta infraestrutura, que é a adequação do padrão Darwin Core (“DwC”) para atender parte significativa da demanda de integração de dados, no escopo do projeto citado.

## Uma visão para a arquitetura

Primeiramente, é preciso considerar que o desenvolvimento e evolução do DwC foi guiado por dois princípios: flexibilidade e adaptabilidade. Isso fez com que ele fosse “estendido” pela comunidade para representar e intercambiar dados de diferentes domínios, sempre associados aos seus dois “cores” principais: espécies e ocorrências [3].

Estes princípios vem bem à calhar, pois é razoável pensar que, dependendo da demanda do MMA em dados sobre espécies ameaçadas e sua conservação, é possível customizar o DwC para que possa ser utilizado pelas instituições vinculadas, produtoras e detentoras de dados, para “entregar” os dados ao MMA, de forma que este possa integrá-los e proceder aos processos de síntese e análise para tomada de decisão.

Em uma visão geral de arquitetura, podemos considerar o seguinte:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/lampadaAbajur3.png)

Aqui creio ser necessário deixar claro algumas ressalvas:

* A visão acima considera apenas dados estruturados de ocorrências e espécies (e suas características ou informações relacionadas), tendo em vista o foco (core) do padrão DwC;
* Por conta disso, a visão acima não considera outros dados fundamentais na tomada decisão em conservação, que são dados espacializados em formato vetorial (shapes) ou matriciais (raster), nem dados estruturados sobre outras entidades diferentes de ocorrências e espécies, como por exemplo ambientais, vetores de pressão etc;
* Assim sendo, a visão de uma “Infraestrutura de Dados sobre Biodiversidade do MMA e Vinculadas” vai muito além desta representação;
* Não estão representadas na figura acima atividades relacionadas a síntese e análise dos dados, que convido os leitores a ler nesta outra postagem.

## Estendendo o padrão DwC

Apesar da significativa evolução do DwC e suas extensões no sentido de atender a crescente demanda de áreas específicas[3], os processos de síntese e análise do MMA demandam conjuntos de dados que são peculiares ao cenário social, ambiental, jurídico e econômico nacional.

Assim sendo, há algum tempo chegamos a esboçar, juntamente com o MMA e o ICMBio, uma customização do padrão DwC para atender a uma demanda pontual do MMA, mas que consideramos que seria recorrente.  Chamamos o formato de MMA-Darwin Core (MMA-DwC).

É importante destacar aqui que o exercício, não globa todos os dados produzidos ou sob a guarda das instituições vinculadas citadas, nem estressa os dados necessários ao MMA para tomada de decisão. Ou seja, não passou de um exercício. Contudo, o que chamo a atenção aqui é que, neste domínio de ocorrências e espécies coberto pelo padrão DwC, é possível estendê-lo de forma a possibilitar o acesso, consumo, integração e análise destes dados por parte do MMA, subsidiando processos de tomada de decisão e formulação de políticas públicas.

Não pretendo entrar em detalhes aqui de interoperabilidade ou do padrão DwC em si. Caso o leitor tenha interesse em se aprofundar tecnicamente nesta área, sugiro iniciar com o documento Diretrizes para Integração de Dados de Biodiversidade, já citado aqui e publicado pelo MMA.

Fico na expectativa que no âmbito do projeto citado, possamos evoluir na discussão de aspectos desta Infraestrutura de Dados, e sua implementação.

## Referências

[1] Darwin Core Task Group, Biodiversity Information Standards (TDWG). 2009. Darwin Core.
http://rs.tdwg.org/dwc/ (acessado em 09/12/2016).

[2] Silva, D.L.; Corrêa, P.L.P.; Juarez, K.M.; Fonseca, R.L. 2015. Diretrizes para Integração de Dados de Biodiversidade. Brasília: MMA, 100p.

[3] Wieczorek J, Bloom D, Guralnick R, Blum S, Döring M, Giovanni R, et al. 2012. Darwin Core: An Evolving Community-Developed Biodiversity Data Standard. PLoS ONE 7(1): e29715. doi:10.1371/journal.pone.0029715.



