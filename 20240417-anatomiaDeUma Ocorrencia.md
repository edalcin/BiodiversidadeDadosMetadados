# Anatomia de uma ocorrência

## 17 de abril de 2024

Era dois de março de 2004 e o verão estava chegando ao fim. A expedição ao Parque Estadual do Desengano, no Rio de Janeiro, formada por oito pesquisadores, avistou um afloramento rochoso à direita da estrada que leva a entrada do Parque Estadual do Desengano à Morumbeca. Resolveram parar. A Dra. Rafaela Forzza percebeu uma população de indivíduos da família Bromeliaceae – família botânica de seu interesse – e resolveu coletar dez exemplares para estudos posteriores na instituição, sob o número 2843, em sua caderneta de coleta. Ela anota a localização, tirada do equipamento de GPS: 21º 52.54′ S e 41º 56.36’W; e anota a altitude oferecida também pelo GPS: 683 m.s.m.

Como de costume, a descrição do material também é anotada em sua caderneta de campo:


>Erva 3m alt., folhas verde-claras com bainha castanha, escapo rosado, brácteas do escapo rosadas na base, verdes no ápice, primarias rosa, raque verde clara, bráctea floral e sépalas amarelas, pétals alvas passando a amarelas, androceu e gineceu alvos, aroma adocicado, suave, 9 ex (exemplares).


De volta ao Instituto de Pesquisas Jardim Botânico do Rio de Janeiro (JBRJ) um dos nove exemplares foi tombado junto ao Herbário Dimitri Sucre, sob o no. de tombo RB 402256 (“otherCatalogNumbers”) e, seguindo a boas práticas, os exemplares restantes foram compartilhados com os herbários SP, SPF, MO, K (2 exemplares), MBM, NY, CEPEC e CTES, conforme descrito na etiqueta anexada ao material do JBRJ. Nestas instituições, as exsicatas foram acolhidas e catalogadas em seus sistemas de registro sob os seguintes números (ou “catalogNumber”, segundo o padrão Darwin Core):

| Herbário | Sigla | No. de Catálogo |
| --- | --- | --- |
| Herbário Maria Eneyda P. K. Fidalgo | SP | 371976 (SP371976) |
| Departamento de Botânica – Universidade de São Paulo | SPF | Não Localizada |
| Missouri Botanical Garden | MO | MO1527603 |
| Kew Gardens | K | K000976359<br>K000976360 |
| Prefeitura Municipal de Curitiba – Museu Botânico Municipal | MBM | MBM297705 |
| New York Botanical Garden | NY | NY01018075 |
| “Andre Mauricio Vieira de Carvalho” – CEPEC – Centro de Pesquisas do Cacau | CEPEC | CEPEC00101880 |
| Instituto de Botánica del Nordeste – Argentina | CTES | Não Localizada |

Com duas amostras não localizadas – CTES e SPF, estas sete amostras se somam a amostra catalogada no herbário do Jardim Botânico do Rio de Janeiro, sob o número RB00177367 (“catalogNumber“), totalizando 8 amostras do que é considerado “uma mesma ocorrência”. Este é o cenário da relação do evento da coleta “Forzza 2843” com suas amostras:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/anatomia1.png)

Agora começa a ficar “divertido”! Perceba que o conceito de “ocorrência”, segundo o padrão Darwin Core (DwC) é:

>"An existence of a dwc:Organism at a particular place at a particular time."

E, para identificar este fato único, no tempo e no espaço, ainda segundo o padrão DwC, seu identificador é o termo “ocurrenceID”, que deveria ser um identificador global único representando aquele fato no tempo e no espaço. Entretanto, na prática, não é o que ocorre. Como cita (NELSON; SWEENEY; GILBERT, 2018):

>"…Depending on the properties being invoked, a herbarium specimen is at once an Occurrence and a materialSample, as each of these has overlapping properties. In many cases, an Occurrence could be considered equivalent to a herbarium specimen from a DwC per- spective; however, in the case of duplicates from the same organism, technically all of the specimens represent the same Occurrence and thus should all have the same occurrenceID…"

Aqui deixamos claro que, tecnicamente, o correto seria que estas amostras da mesma ocorrência compartilhassem o mesmo “occurrenceID”, guardando sua individualidade nos seus “catalogNumber”. Mas não é o que ocorre:

| catalogNumber | ocurrenceID |
| --- | --- |
| SP371976 | BRA:IBT:SP:371976 |
| MO1527603 | 3420129 |
| K000976359 | 2019573 |
| K000976360 | 2146332 |
| MBM297705 | urn:catalog:MBM:297705 |
| NY01018075 | 3099084 |
| CEPEC00101880 | 2846238 |
| RB00177367 | urn:catalog:JBRJ:RB:177367 |

Entretanto, para os sistemas agregadores de dados e consumidores (descuidados), estes dados acabam por representar, equivocadamente, oito diferentes ocorrências, inflacionando perigosamente as análises baseadas nestes dados.

Mas fica ainda melhor! Ainda temos os escopos taxonômico, espacial e temporal para considerar. Lembram que o conceito de ocorrência é “An existence of a dwc:Organism at a particular place at a particular time”? Vamos ao escopo “time”, com seus termos de representação no DwC:

| catalogNumber | eventDate | verbatimEventDate | year | month | day |
| :--- | :---: | :---: | ---: | ---: | ---: |
| SP371976 |  |  | 2004 | 03 | 02 |
| MO1527603 | 2/3/2004 |  | 2004 | 3 | 2 |
| K000976359 | 3/2/2004 | 2004-02-03 | 2004 | 2 | 3 |
| K000976360 | 2/3/2004 | 2004-03-02 | 2004 | 3 | 2 |
| MBM297705 | 2004-3-2 |  | 2004 | 3 | 2 |
| NY01018075 | 2/3/2004 | 2004-03-02 | 2004 | 3 | 2 |
| CEPEC00101880 | 2/4/1992 | 2/4/1992 | 1992 | 4 | 2 |
| RB00177367 | 2004-03-02 |  | 2004 | 03 | 02 |

Pontos de atenção:

* Considerando que o padrão DwC recomenta que o “eventDate” seja “…to use a date that conforms to ISO 8601-1:2019”, o registro do JBRJ é o único que atende a recomendação;
* Para “month” e “day”, não é recomendado o uso do prefixo “0”, como em SP e RB;
* K parece ter interpretado o “dia” como “mês”, e o “mês” como “dia”, em K000976359:
* CEPEC só concorda com o “dia” da coleta.

Vamos agora considerar o conceito do “espaço”:

| catalogNumber | decimalLatitude | decimalLongitude | verbatimLatitude | verbatimLongitude |
| :--- | ---: | ---: | ---: | ---: |
| SP371976 | -21.8816670000000002 | -41.9433330000000026 |  |  |
| MO1527603 | -218.83305555555555 | -419.3330555555556 |  |  |
| K000976359 | -21.881666666666668 | -41.94333333333333 |  |  |
| K000976360 | -21.865000000000002 | -41.94333333333333 |  |  |
| MBM297705 |  |  |  |  |
| NY01018075 | -21.8755555555555574 | -41.9394444444444403 |  |  |
| CEPEC00101880 |  |  |  |  |
| RB00177367 | -21.8816667 | -41.9433333 | 21º52´54´´ | 41º56´36´´W |

Pontos de destaque:

* Chama a atenção as diferentes “precisões”, representadas em casas decimais, para a mesma ocorrência;
* Acredito que a conversão da coordenada expressa como “verbatim”, presente na etiqueta de coleta anexada às duplicatas, em diferentes sistemas e “DATUM”, possa ter causado a inconsistência;
* CEPEC e MBM não consideram coordenadas geográficas em seus registros, ou não exportam;
* MO parece ter se equivocado no valor inteiro, pulando uma casa para o ponto decimal.

Um outro atributo de uma ocorrência é o “coletor”, visto que o conjunto “coletor” (dwc:recordedBy)+ “numero de Coleta” (dwc:recordNumber) são identificadores muito utilizados para uma ocorrência. Entretanto, da mesma forma, eles nem sempre são consistentes entre as amostras:

| catalogNumber | recordedBy |
| :--- | :--- |
| SP371976 | Forzza, RC; et al. |
| MO1527603 | Rafaela C. Forzza, Leandro C. S. Assis, Jomar G. Jardim, L.R. Lima;E. Lucas |
| K000976359 | R.C. Forzza;J.G. Jardim,L.R. Lima,D. Zappi,L.C.S. Assis,E. Lucas,S. Edwards,B.r. Silva |
| K000976360 | R.C. Forzza;J.G. Jardim,B.R. Silva,L.R. Lima,D. Zappi,L.C.S. Assis,E. Lucas,S. Edwards |
| MBM297705 | Forzza, RC; et al. |
| NY01018075 | R. C. Forzza |
| CEPEC00101880 | R. C. Forzza |
| RB00177367 | R.C. Forzza; et al. |

Apenas NY e CEPEC concordam com a representação de quem foi o coletor das amostas.

Por fim, vamos considerar o escopo taxonômico:

| catalogNumber | scientificName |
| :--- | :--- |
| SP371976 | Alcantarea heloisae |
| MO1527603 | Alcantarea odorata (Leme) J.R. Grant |
| K000976359 | Alcantarea heloisae J.R.Grant |
| K000976360 | Alcantarea odorata (Leme) J.R.Grant |
| MBM297705 | Alcantarea odorata (Leme) J.R.Grant |
| NY01018075 | Alcantarea odorata (Leme) J.R.Grant |
| CEPEC00101880 | Alcantarea odorata |
| RB00177367 | Alcantarea heloisae J.R.Grant |

Duas espécies válidas (nomes aceitos) foram consideradas nas diferentes instituições.

Em resumo, considerando apenas um sub-conjunto de atributos de uma ocorrência, este é o cenário:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/anatomia2.png)

Olhando apenas para o conjunto de dados associados às amostras. Podemos considerar que são “coisas diferentes”. Infelizmente, sem o contexto, muitas análises e sínteses de conhecimento acabam por acreditar nisso.

## Considerações:

Os dados de ocorrência publicados em repositórios temáticos, como o Integrated Publishing Toolkit (IPT), e agregados pelo GBIF e SiBBr, por exemplo, são notoriamente “sujos” (RIBEIRO et al., 2022; DOREY et al., 2023). Porém, Infelizmente, é neste cenário de absoluta inconsistência que algumas análises se apoiam. Mesmos grandes mapas “plotando” ocorrências, em “sites” de instituições agregadoras como GBIF e SiBBr acabam por mostrar uma imagem absolutamente impactante de “ocorrências”. Porém, absurdamente inflacionadas, e que estão longe de representar a realidade do fato biológico.

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/anatomia3.png)

Para piorar um cenário que já é ruim, algumas coleções publicam seus dados em mais de um “repositório IPT”, o que acaba por promover uma redundância de registros ainda maior.

Além disto, trabalhos, teses, dissertações, e mesmo avaliações do status de conservação, em sua avassaladora maioria, não trazem o detalhamento das etapas de tratamento, limpeza e harmonização dos dados de ocorrência considerados.

Carecemos de padrões, protocolos e, em última instância, governança sobre estes dados, em escalas regional, nacional e mesmo global. O trabalho e re-trabalho de verificação, validação e harmonização deste conjunto gigantesco de dados de “ocorrências” é enorme e, em minha modesta opinião, tem atrasado a produção de informação relevante, quando não acaba produzindo informação com um nível de incerteza inaceitável para tomada de decisão e formulação de políticas públicas.

Creio ainda que os dados de ocorrências em coleções científicas, o qual são a base da pirâmide do conhecimento da biodiversidade, são, de certa forma, negligenciados como objeto primário das análises. Parece que o conjunto de dados publicados que os representam no mundo virtual são priorizados na melhoria da qualidade, com ferramentas e algoritmos informatizados, enquanto o objeto físico na coleção em si permanece, por diversas razões, com baixa qualidade em seus “metadados” associados. É como dar mais importância à etiqueta da embalagem do que ao conteúdo do pacote!

Gerir uma coleção física, como as exsicatas em um herbário, por exemplo, requer recursos humanos, financeiros e materiais significativos. Gerir um conjunto de dados requer apenas um computador ligado na tomada e na internet. Ambos os acervos – físico e virtual – necessitam de recursos humanos com diferentes competências em sua gestão. Entretanto, o acervo virtual é, ou deveria ser, uma representação fiel do acervo físico. Aprendi com meus mestres-jedi que “bancos de dados nada mais são que representações do mundo real”. Quando conjuntos de dados são transformados – limpos – para uma análise eles deixam de representar o acervo físico. Se tornam uma abstração criada pelo analista e seus algoritmos, que existe de forma efêmera e particular àquela análise, perdendo a relação de identidade com o acervo físico, ou seja, com o fato biológico no tempo e espaço.

Penso que estamos gastando muito tempo e recursos arrumando, agregando e publicando dados, e dedicando pouco tempo e recursos para qualificar, organizar e preservar adequadamente as coleções físicas.

## Nota Final

Estas considerações foram feitas – apenas e exclusivamente – com base dos dados ofertados pelos seguintes IPTs, nas seguintes versões e datas:

| No de Catálogo | URL do recurso no IPT correspondente | versão | data |
| :--- | :---: | ---: | ---: |
| SP371976 | http://ipt1.cria.org.br/ipt/resource?r=sp_fanerogamas | v1.105 | 2024-03-10 |
| MO1527603 | https://ipt.jbrj.gov.br/reflora/resource?r=moh | v1.225 | 2024-01-01 |
| K000976359 | https://ipt.jbrj.gov.br/reflora/resource?r=k_reflora | v1.227 | 2024-01-01 |
| MBM297705 | https://ipt.jbrj.gov.br/jabot/resource?id=mbm | v1.10 | 2024-04-01 |
| NY01018075 | https://ipt.jbrj.gov.br/reflora/resource?r=nyh | v1.224 | 2023-11-22 |
| CEPEC00101880 | https://ipt.jbrj.gov.br/reflora/resource?r=cepec_herbarium | v1.285 | 2024-01-01 |
| RB00177367 | https://ipt.jbrj.gov.br/jbrj/resource?r=jbrj_rb | v84.253 | 2024-03-12 |

Sugestões, críticas e comentários são sempre bem-vindos!

## Referências

DOREY, James B.; FISCHER, Erica E.; CHESSHIRE, Paige R.; NAVA-BOLAÑOS, Angela; O’REILLY, Robert L.; BOSSERT, Silas; COLLINS, Shannon M.; LICHTENBERG, Elinor M.; TUCKER, Erika M.; SMITH-PARDO, Allan; FALCON-BRINDIS, Armando; GUEVARA, Diego A.; RIBEIRO, Bruno; DE PEDRO, Diego; PICKERING, John; HUNG, Keng-Lou James; PARYS, Katherine A.; MCCABE, Lindsie M.; ROGAN, Matthew S.; … COBB, Neil S. A globally synthesised and flagged bee occurrence dataset and cleaning workflow. Scientific Data, v. 10, n. 1, p. 747, 2 nov. 2023. https://doi.org/10.1038/s41597-023-02626-w.

NELSON, G.; SWEENEY, P.; GILBERT, E. Use of globally unique identifiers (GUIDs) to link herbarium specimen records to physical specimens. Applications in Plant Sciences, v. 6, n. 2, p. e1027, 2018. https://doi.org/10.1002/aps3.1027.

RIBEIRO, Bruno R.; VELAZCO, Santiago José Elías; GUIDONI‐MARTINS, Karlo; TESSAROLO, Geiziane; JARDIM, Lucas; BACHMAN, Steven P.; LOYOLA, Rafael. bdc : A toolkit for standardizing, integrating and cleaning biodiversity data. Methods in Ecology and Evolution, v. 13, n. 7, p. 1421–1428, jul. 2022. https://doi.org/10.1111/2041-210X.13868.