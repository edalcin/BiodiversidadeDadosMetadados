# Avaliação rápida de risco de extinção
## 12 de Outubro de 2016

Em 21 de dezembro de 2006 a CONABIO publicou sua resolução no 03, trazendo as Metas Nacionais para Biodiversidade que deveriam ter sido atingidas até 2010. A meta 2.7 dizia: “Uma avaliação preliminar do status de conservação de todas as espécies conhecidas de plantas, e animais vertebrados e seletivamente dos animais invertebrados, no nível nacional“. Esta meta continua pendente.Para 2020 a segunda meta da Estratégia Global para Conservação de Plantas é “An assessment of the conservation status of all known plant species, as far as possible, to guide conservation action“.

Por fim, a Portaria no 43 do Ministério do Meio Ambiente, de 31 de janeiro de 2014 define que a avalição de risco de extinção deve ser feita “…de acordo com as definições e critérios da União Internacional para Conservação da Natureza-IUCN…”.

Desde sua criação em 2008, o CNCFlora avaliou o risco de extinção de 5.195 espécies da flora, de um total de 46.097. Ou seja, 11,27%.

Faltando 1.067 dias úteis até 31 de dezembro de 2020 (em 12/10/2016), e 40.902 espécies para avaliar, podemos considerar que, baseado em um cálculo de simplicidade franciscana, avaliando 38.33 espécies por dia, chegaremos em 2020 com a meta atingida!

Entretanto, outro cálculo simplório mostra que nos 11.858 dias úteis de existência do CNCFlora, foi possível avaliar o risco de extinção de 5.195 espécies, o que nos dá uma taxa de 2,28 espécies/dia útil, levando para 17.939,5 dias necessários para avaliar o risco de extinção de toda a flora brasileira. Considerando os dia corridos, se começássemos amanha, 13/10/2016, terminaríamos em 24/11/2065. Pouco mais de 49 anos de trabalho.

É claro que esta estimativa é absolutamente imprecisa, pois as variáveis que influenciam na taxa de avaliação/dia não foram consideradas. Porém, uma estimativa é melhor que nenhuma. Esta é baseada em evidências, e em uma média de oito anos de atuação do CNCFlora.

O ponto que quero levantar aqui é que, citando o Coordenador do CNCFlora, Dr. Gustavo Martinelli, “é preciso ganhar escala“! Assim, quero compartilhar com vocês uma abordagem computacional para ajudar neste processo.

## A proposta

O processo de avaliação de risco de extinção, resumidamente, utiliza-se da análise de dados disponíveis e da a aplicação de critérios, conforme a figura abaixo[1]:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/avaliacaoRapidaRiscoExtencao1.png)

No fluxo destacado em vermelho, considera-se que com registros de ocorrência de uma espécie, é possível realizar cálculos geoespaciais de extensão de ocorrência (EOO) e área de ocupação (AOO), segundo descritos em IUCN 2012[2]. Além destes dois cálculos, também é possível realizar o cálculo de subpopulações, utilizando o método “circular buffer”[3]. E, com base nestes cálculos, aplicar o “Critério B”, que diz o seguinte:

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/avaliacaoRapidaRiscoExtencao2.png)

Considerando que hoje temos disponíveis milhões de dados de ocorrência em formato digital, e que temos também uma lista oficial da flora do brasil em formato digital, é possível desenvolver uma ferramenta computacional capaz de, automaticamente, buscar dados de ocorrência para espécies da flora do Brasil, realizar os cálculos espaciais e avaliar o risco de extinção destas espécies, de acordo com o “Critério B” da metodologia da IUCN.

## A ferramenta

Com base nestas considerações, foi possível desenvolver a ferramenta “Rapid Risk Assessment Applicacion (RRAPP)”

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/avaliacaoRapidaRiscoExtencao3.png)

Nesta versão, a ferramenta consome dados da lista de espécies da flora do Brasil disponíveis via IPT e dados de ocorrência para estas espécies, disponíveis nos IPTs do Herbário RB e do SiBBr, realiza os cálculos espaciais e gera uma interface de consulta com os resultados da avaliação de risco de extinção.

Mais detalhes sobre a ferramenta podem ser vistos na página própria, e no artigo publicado no “WCAMA 2016” – 7º Workshop de Computação Aplicada à Gestão do Meio Ambiente e Recursos Naturais.

O potencial desta ferramenta é espetacular pois ela é capaz de realizar a cada 24hs, por exemplo,  o risco de extinção de toda a flora de um país, com base no “critério B”. Em minha opinião, esta ferramenta demonstra o uso prático e objetivo para conservação dos dados primários de biodiversidade disponíveis em formato digital, justificando todos os esforços e recursos investidos neste sentido.

A ferramenta está em sua primeira versão e muito ainda precisa ser feito. Não só no aprimoramento da ferramenta em si, mas também fica claro a necessidade de se agregar qualidade taxonômica e espacial aos dados primários hoje disponíveis.

Tenho muito orgulho de ter tido um papel, mesmo que de coadjuvante, nesta ferramenta, onde o protagonista é o arquiteto de sistemas e desenvolvedor Diogo Souza.

## Referências

[1] Rodríguez, Jon Paul, et al. “A practical guide to the application of the IUCN Red List of Ecosystems criteria.” Phil. Trans. R. Soc. B 370.1662 (2015): 20140003.

[2] IUCN. (2012). IUCN Red List Categories and Criteria: Version 3.1. Second edition.
Gland, Switzerland and Cambridge, UK: IUCN. iv + 32pp.

[3] Rivers, M. C., Bachman, S. P., Meagher, T. R., Lughadha, E. N., & Brummitt, N. A. (2010). Subpopulations, locations and fragmentation: applying IUCN red list criteria to herbarium specimen data. Biodiversity and Conservation, 19(7), 2071-2085.
