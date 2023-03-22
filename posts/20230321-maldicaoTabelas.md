# A Maldição das Tabelas
## 21 de Março de 2023

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/maldicaoTabelas1.jpg)

Há algum tempo venho investindo uma parte do meu tempo para ler e aprender sobre novas formas de modelar e estruturar dados. Nestes tempos que vivemos, novas tecnologias estão disponíveis e parece ser razoável considerar novas abordagens para representar o mundo real.

Acredita-se que as primeiras tabelas surgiram com os sumérios, na antiga Mesopotâmia, há cerca de 2.000 anos, e nossa civilização vem usando esta forma de organizar dados desde então. Desde a mais tenra idade, na escola e, quando adultos, no trabalho, somos condicionados a organizar nossos dados em linhas e colunas. Até aqui, neste editor de texto que vos escrevo (e na maioria dos outros), existe um botão onde posso, rapidamente, criar uma tabela. No maravilhoso mundo dos bancos de dados, as tabelas não só prosperaram como, desde 1970, passaram a se relacionar e, pasmem, deste relacionamento passaram a ter filhos! E, como que por encanto, as “planilhas de cálculo” se tornaram a solução, não para calcular, mas para listar e organizar dados. A presença onipotente das linhas e colunas perverteu até o mais ingênuo e inócuo arquivo digital. O “TXT” virou o “CSV” e passou a frequentar a elite do mundo digital.

Entretanto, aprendemos com o “Professor Dalcin”, na primeira aula da disciplina de Gestão de Informação sobre Biodiversidade, que “bancos de dados nada mais são que representações do mundo real” e criar modelos do mundo real com ferramentas limitadas é como tentar representar uma esfera com peças de LEGO®.

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/maldicaoTabelas2.png)

Chegamos então na provocação central deste artigo. O “paradigma” (odeio esta palavra…) de linhas e colunas, juntamente com o robusto e maduro modelo relacional, com sua álgebra relacional, é a melhor ferramenta para organizar dados sobre biodiversidade? Depende. De que “dados sobre biodiversidade” estamos falando?

Sem dúvida alguma, conjuntos de tabelas relacionadas tem seu papel na organização de dados sobre biodiversidade. O que é diferente de dizer que todos os dados sobre biodiversidade são bem representados por conjuntos de tabelas relacionadas.

Alguns conjuntos e dados sobre biodiversidade podem ser melhor representados sob a forma de grafos, como já comentei nesta postagem aqui. E, outra forma de estruturar dados bem popular hoje em dia é sob a foma de documentos, onde o formato mais conhecido é o JSON (JavaScript Object Notation), o filho “celebridade” do XML. Abaixo um exemplo de documento JSON, contendo dados sobre uma espécie:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/maldicaoTabelas3.png)<br>
https://jsoncrack.com/editor?json=6416148abbe4fd1e772fdc13

É claro que modelar e organizar conjuntos de dados tem que considerar a “implementação”. Ou seja, um “sistema gerenciador de banco de dados” (SGBD) capaz de lidar com a estrutura de dados específica. Lá no artigo sobre grafos comentei que experimente o Neo4J. Para lidar com documentos, tenho brincado bastante com o MongoDB, e estou trabalhando em um projeto para desenvolver uma ferramenta para converter arquivos Darwin Core para o formato JSON, que podem ser gerenciados pelo MongoDB, por exemplo.

Porém, o mais fascinante hoje é que estão surgindo soluções de bancos de dados “multi-modelos”, ou seja, que podem lidar com diferentes estruturas de dados (p.ex. grafos, documentos e tabelas) em uma mesma plataforma. Até poucos anos atrás, tínhamos sistemas de “persistência poliglota” (mais de um SDBG), de grande complexidade de implementação e manutenção. Hoje temos alternativas interessantíssimas de SGBDs, capazes de lidar com diferentes modelos de dados, como o ArangoDB, que lida com documentos, grafos e chave/valor; o Fauna (!), que combina o modelo relacional com documentos; e até o “queridinho” dos adeptos do modelo relacional, o PostgreSQL, já admite JSON como um tipo de dados válido em suas tabelas. Ou seja, não é por falta de “implementação” que não estamos avançando em novas, e mais apropriadas, formas de representar dados sobre biodiversidade.

Creio que estamos tão condicionados a pensar sob a forma de linhas e colunas, que chega a ser mais que uma “zona de conforto”. É quase que uma “maldição”! É claro que é preciso {capacitação, competência, etc.} para enxergar o mundo com outros olhos, e passar a utilizar modelos baseados, por exemplo, em documentos ou em grafos. Não necessariamente excludentes aos modelos relacionais clássicos. Porém, precisamos primeiro questionar os modelos existentes, demandar e propor novos modelos baseados em novas abordagens e tecnologias. Talvez, estejamos sofrendo para representar uma esfera, cegos pelas peças de LEGO®, sem olhos para a argila!
