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