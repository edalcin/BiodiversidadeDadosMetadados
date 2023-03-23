# Os contextos da informação sobre Biodiversidade
## 25 de Setembro de 2016

Há algum tempo estou convencido de que a informação sobre Biodiversidade tem quatro contextos fundamentais: O taxonômico, o espacial, o temporal e o temático.

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/contextosInformacaoBiodiversidade1.jpg)

Afinal de contas, baseado na minha experiência, é o que as pessoas querem saber! Por exemplo:

* Quais as espécies de bromélias do Parque Nacional de Itatiaia?
  * Contexto taxonômico: Bromélias
  * Contexto espacial: Parque Nacional de Itatiaia
* Quais as plantas utilizadas pelas tribos do Parque Indígena do Xingu?
  * Contexto taxonômico: plantas
  * Contexto espacial: Parque Indígena do Xingu
  * Contexto temático: plantas úteis
* Quais as espécies de plantas ameaçadas de extinção da lista de 1998 que ocorrem em áreas protegidas?
  * Contexto taxonômico: plantas
  * Contexto espacial: áreas protegidas
  * Contexto temático: plantas ameaçadas
  * Contexto temporal: 1998
* Quais as espécies de pteridófitas ocorriam aqui antes da Barragem de Sobradinho?
  * Contexto taxonômico: pteridófitas
  * Contexto espacial: área do lago de Sobradinho
  * Contexto temporal: até 1973
* Quais as espécies de fanerógamas polinizadas por beija-flores?
  * Contexto taxonômico: fanerógamas e beija-flores
  * Contexto temático: relação ecológica de polinização

E por ai vai...

Na prática, acredito que "99%" dos "casos de uso" se encontram na interseção destes quatro possíveis conjuntos. Ficaria muito feliz se alguém apresentasse ai embaixo nos comentários algum exemplo que corresponda ao 1% que acredito existir, e que não se encaixa nestes quatro contextos fundamentais.

Considerando isto, em nosso exercício de implementação de uma arquitetura para publicação de informações sobre biodiversidade, estamos procurando definir um esquema que poderia ser utilizado para indexar diferentes recursos de informação sobre biodiversidade com base nestes contextos. Ou seja, catalogar os metadados destes recursos e classificá-los nestes quatro contextos.

Ando estudando bastante novas tecnologias e ferramentais, pois decidi colocar a "mão na massa". Desde meu doutorado não programava nem mexia com Bancos de Dados e, desde então, o mundo mudou bastante! Estou estudando (e entusiasmado!) com Elasticsearch e JSON pois, pelo que vi até agora, o Elasticsearch é uma ferramenta espetacular para abordar este problema. Estou experimentando, na prática, algumas abordagens para esta estrutura. Quem quiser acompanhar o projeto tecnicamente, e até contribuir, pode conferir e acompanhar a página do projeto no GitHub.
