# “Por mares nunca dantes navegados…”

## 05 de março de 2024

Ando sumido. Fato. Porém, por uma “boa causa”, que gostaria de compartilhar com vocês.

Desde meu artigo sobre “[a maldição das tabelas](https://github.com/edalcin/BiodiversidadeDadosMetadados/blob/main/posts/20230321-maldicaoTabelas.md)“, onde compartilhei minha iniciação com [JSON](https://www.w3schools.com/js/js_json_intro.asp), para estruturar dados em documentos; e com o [MongoDB](https://www.mongodb.com/), para lidar com estes documentos, estou irremediavelmente amaldiçoado enfeitiçado pela dupla “JSON-MongoDB”.

Assim, resolvi partir “por mares nunca dantes navegados” e iniciei um projeto com meu fiel, incansável e talentoso parceiro [Henrique Pinheiro](https://www.linkedin.com/in/phenome/), que chamamos de “[DarwinCore2JSON](https://github.com/edalcin/DarwinCoreJSON)” (Github em constante atualização).

No início, este projeto tinha a intenção de converter os arquivos Darwin Core da [Flora e Funga do Brasil](https://floradobrasil.jbrj.gov.br/consulta/) para JSON e carregar estes documentos no MongoDB. O objetivo do projeto era apenas [este](https://github.com/edalcin/DarwinCoreJSON/blob/main/README.v1.md). Entretanto, com o “andar da carruagem”, o projeto mudou de [foco e de propósito](https://github.com/edalcin/DarwinCoreJSON/blob/main/README.v2..md).

Em essência, ficou claro para mim que havíamos criado a capacidade de ter em um único banco de dados os nomes do [Catálogo Taxonômico da Fauna do Brasil](http://fauna.jbrj.gov.br/fauna/listaBrasil/PrincipalUC/PrincipalUC.do?lingua=pt), da Flora e Funga do Brasil, e ainda associar a estes cerca de 12 milhões de registros de ocorrências, permitindo que se faça, em um único ambiente, perguntas, análises e visualizações que não estavam disponíveis em nenhum outro ambiente ou plataforma. Isso consistia em um recurso extraordinário e, até então, inexistente. Vale notar aqui que existe o [“Atlas” do Sistema de Informações sobre a Biodiversidade Brasileira](https://sibbr.gov.br/). Porém, possui uma proposta diferenciada e, se comparado com a base do DarwinCore2JSON, dados um pouco desatualizados.

Era possível pesquisar, de forma rápida e simples, em milhões de registros de exsicatas, uma lista de ocorrências onde havia a palavra “medicinal” das observações das coletas, associada ao hábito “árvore” e ao bioma “caatinga”, estes dois últimos vindos da Flora e Funga do Brasil. As possibilidades eram enormes, pois, além de ter estes conjuntos de dados integrados, não havia a limitação de pesquisas pré-definidas imposta por um “sistema” ou “painel”. Uma vez dominada a sintaxe de [query](https://www.mongodb.com/docs/manual/tutorial/query-documents/) (MQL – Mongo Query Language) e a funcionalidade maravilhosa do ___[aggregation pipeline](https://www.mongodb.com/docs/manual/core/aggregation-pipeline/)___, você estava com a faca, o queijo, a manteiga, o pão e tudo mais na mão!

O primeiro grande insight foi de perceber o quanto ficamos limitados por “sistemas”, “painéis” e qualquer outra interface que encerre um conjunto finito de opções de filtragem e indexação dos dados. São aceitáveis para atender pesquisas simples, como “uma lista de árvores da Mata Atlântica”, mas ineficientes em consultas mais complexas, como, por exemplo, “quais as ervas ou subarbustos de flores brancas, com observações de uso medicinal, que ocorrem no Caparaó”.

Resultado:

* Borreria verticillata (L.) G.Mey.
* Polygala paniculata L.

[Aqui está o resultado da consulta, com a ficha das espécies e todas as ocorrências associadas](http://dalcinweb.s3-website-us-east-1.amazonaws.com/blog/maresnuncadantes/dwc2json.taxaOccurence.json) (escolha “salvar como…”).

Minha percepção é que cientistas de dados, que “moem e mastigam” dados para gerar informação relevante, torcem o nariz para sistemas e painéis. Os usam somente para baixar todos os dados, de forma bruta e concreta, que precisam para proceder suas análises, pois não conhecem os detalhes dos filtros utilizados por baixo das interfaces. E ainda, precisam dos dados brutos, mas estruturados, para rodar em seus scripts, em “R”, por exemplo. Por sua vez, sistemas são excelentes para possibilitar humanos interagir com os dados, especialmente na criação, e edição de registros. Seria impossível construir uma Flora e Funga do Brasil sem o excelente sistema que permite que os especialistas contribuam com o conteúdo. Porém, ofertar os dados “brutos e completos” como faz via [IPT](https://www.gbif.org/ipt), permite que os analistas manipulem e integrem estes dados da forma mais conveniente possível, promovendo a identificação de padrões e a geração de novo conhecimento.

Vale notar que o projeto [DarwinCore2JSON](https://github.com/edalcin/DarwinCoreJSON) permite que toda a base de dados seja atualizada “com um click”, o que leva alguns minutos. Poderia ser programado para atualizar todos os {meses, semanas, dias, horas etc}, pois ele vai nos IPTs, baixa os dados, formata em JSON e insere na base de dados do MongoDB, tudo automaticamente.

Infelizmente ainda não consegui integrar os dados de “risco de extinção”, pois até a presente data estes dados – das espécies avaliadas pelo CNCFlora e ICMBio – ainda não estão disponíveis no IPT em formato e completude apropriados. Uma vez integrados, perguntas incluindo a categoria de risco de extinção agregariam um valor extraordinário para conservação, como, por exemplo, as espécies X, Y e Z que estão na categoria de “vulnerável” e não há registro de coleta em nenhuma unidade de conservação.

Sim! Esqueci de mencionar que o MongoDB possui uma capacidade de realizar queries espaciais, nativamente, uma vez que as coordenadas estejam em [GeoJSON](https://geojson.org/)! Por conta disto, já convertemos todas as coordenadas existentes nos 12 milhões de registros de ocorrência da base, para o formato GeoJSON e é possível perguntar, por exemplo, quais as espécies de plantas estão presentes em um raio de 10km de um registro de ocorrência de uma ave.

Este artigo já está ficando bem extenso e não quero ocupar muito o seu tempo. Mas quero compartilhar ainda o outro projeto que estou envolvido, com a querida amiga [Viviane Kruel](http://lattes.cnpq.br/0560294487722709), referência na Etnobotânica, que tem tudo a ver com este: um banco de dados (em JSON, e no MongoDB) “de espécies de plantas nativas ou de ampla distribuição, com registros de usos como medicinal no Brasil tendo como “raiz” o seu nome vernacular“.

Agregando este tema, novas perguntas podem ser feitas em uma base que já tem ocorrências e as fichas da Flora e Funga do Brasil. Além disso, resolvemos experimentar colocar o nome vernacular como “raiz” dos dados, associando os nomes científicos da Flora e Funga como um atributo para estes nomes. Até onde pude encontrar, esta proposta é uma verdadeira inovação, visto que todos os bancos de dados sobre plantas de uso medicinal tem como “raiz” o nome científico, com os nomes vernaculares como atributo.

O repositório e seu conteúdo e textos estão sob constante atualização. Porém, os resultados já são bem interessantes enxergando os dados por essa ótica. A flexibilidade dos [bancos de dados orientados a documentos (“schemaless “)](https://www.mongodb.com/unstructured-data/schemaless) “cai como uma luva” para lidar com a heterogeneidade dos dados, “assim como de conhecimentos, procedências e formas de registrar conhecimentos” (Obrigado Viviane , pelo complemento!) relacionados com plantas tidas como medicinais e seu uso pela população.

Ambos os projetos estão em pleno desenvolvimento e, sem recurso algum, exceto valorosos voluntários e alunos, vão andando conforme nossa disponibilidade.

Se você quer ter acesso à base de dados, basta solicitar aí nos comentários e começamos a conversar sobre isso. A ideia é que a base seja pública mesmo, mas hoje ela roda em um servidor próprio. Estou aguardando migrar para infraestrutura institucional para ofertar de forma explícita o acesso. Uma vez utilizada, ela pode ser citada desta forma:

Henrique Pinheiro, & Eduardo Dalcin. (2024). edalcin/DarwinCoreJSON: Segundo Release para o Zenodo. Zenodo. https://doi.org/10.5281/zenodo.10782707

Aguardem mais novidades! Sugestões, comentários e perguntas são sempre bem-vindas!

---

Sobre o título:

Retirado da primeira estrofe de Os Lusíadas – Canto Primeiro, por Luís Vaz de Camões. No Canto Primeiro o poeta se propõe a cantar os feitos heroicos dos soldados e navegadores portugueses, bem como a memória dos reis portugueses que expandiram as fronteiras lusas e a fé cristã.

