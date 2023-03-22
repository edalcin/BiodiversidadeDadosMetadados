# Sonhando com um lago
## 02 de Junho de 2018

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/sonhandoLago1.jpg)

Há algum tempo um lago tem frequentado meus sonhos. Explico.

Há muito e muito tempo atrás, em 2010 (percepção de tempo ajustada para falar de tecnologia), um sujeito chamado James Dixon publicou em seu blog algumas considerações:

* 80-90% das empresas estão lidando com dados estruturados ou semi-estruturados (não desestruturados).
* A origem dos dados é tipicamente um único aplicativo ou sistema.
* Os dados são geralmente subtransacionais ou não transacionais.
* Existem algumas perguntas conhecidas para perguntar sobre os dados.
* Existem muitas perguntas desconhecidas que surgirão no futuro.
* Existem várias comunidades de usuários que têm perguntas sobre os dados.
* Os dados são de uma escala ou volume diário, de modo que não se ajustam técnica e / ou economicamente a um RDBMS.

Minha percepção é que podemos estabelecer aqui uma identificação com os dados sobre Biodiversidade. Apesar de termos um volume considerável de dados “transacionais” estruturados (considerando aqui uma “coleta” como uma “transação” que “registra um fato que aconteceu em um determinado momento no tempo“), devemos considerar todo o conhecimento acumulado e sistematizado em documentos não estruturados, como livros, teses, relatórios etc. Por exemplo, a Biodiversity Heritage Library possui hoje 138.205 títulos distribuídos em 227.549 volumes e 546.592.294 páginas de texto sobre biodiversidade. Aliado a isso, os dados sobre biodiversidade estão, via de regra, fortemente atrelados a um único aplicativo ou sistema, apesar do grande avanço dos padrões e agregadores de dados; e estamos chegando em uma escala (e variedade) de dados que bancos de dados convencionais tem tido dificuldade de lidar.

No mesmo “post” Dixon criou um termo – “Data Lake” – que expressa um conceito. Mais precisamente, uma arquitetura de dados que é considerara por alguns como a evolução de outro conceito: o “Data Warehouse“.

Topei com este termo bem mais tarde em uma postagem do Martin Fowler, sujeito que acompanho e admiro, e a idéia de um “lago de dados sobre biodiversidade” vem me assombrando desde então.

Mas afinal, o que é um “Lago de Dados“? Em resumo, um Lago de Dados é um repositório centralizado que permite armazenar todos os seus dados estruturados e não estruturados em qualquer escala. Você pode armazenar seus dados no estado em que se encontram e executar diferentes tipos de análises – de “dashboards” a processamento de big data, análises em tempo real e aprendizado de máquina – para subsidisiar tomada de decisão.

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/sonhandoLago2.jpg)<br>
_Fonte: https://canaltech.com.br/infra/EMC-oferece-solucao-de-armazenamento-e-analise-de-Data-Lake/_

Não pretendo aqui discutir implementações técnicas até porque tenho sérias limitações neste sentido, apesar de andar lendo um bocado sobre o tema (o “ecossistema Hadoop” agora faz parte dos meus pesadêlos). Aliás, o que vim fazer aqui era contar meu sonho! Voltemos à ele…

Eu sonhei que era um ~~unicórnio azul~~ estava em um deserto de informações sobre biodiversidade. O sol era escaldante e inclemente. Estava andando há vários dias em busca de uma decisão baseada em fatos e quando estava quase cedendo à uma decisão baseada em acordo político, surgiu um lago no horizonte!

Ao me aproximar percebi que neste lago havia toda a informação que eu precisava para tomar uma decisão qualificada. Eram dados brutos de diferentes fontes e formatos, como peixes, nadando para lá e para cá. Furtivos e escorregadios. Para minha sorte, na margem haviam cientistas de dados, sob a forma de pescadores que, munidos de diferentes ferramentas – caniços, tarrafas, redes etc., regozijavam-se com a fartura!

Os peixes pescados eram levados à um restaurante, também à margem do lago (Pare! Essa analogia só fará sentido se você fizer uma pequena pausa para ler isso aqui.), onde eu fui convidado à entrar e saciar minha fome de informação. Acordei renovado de esperanças!

Voltando ao mundo dos mortais, o que são os sonhos senão para serem perseguidos, certo? Conversas lá e acolá e, se o primeiro passo para construir um lago é cavar, já ando de pá na mão buscando parcerias. Vez em quando me vem esses arroubos de esperança e otimismo, mas reconheço que é difícil encontrar parceiro pra cavar um buraco no deserto. Fica mais fácil quando se explica o porquê e pra que né? Então, pronto!
