# Um Assistente pra chamar de seu
## 13 de Agosto de 2020

![](http://dalcinweb.s3-website-us-east-1.amazonaws.com/github/BiodivDadosMeta/assistentePraChamarSeu1.jpg)

Neste mundo digital sobrecarregado de informações, encontrar exatamente o que se quer é uma tarefa árdua e, via de regra, frustrante. As empresas descobriram isso muito rápido, quando clientes tentam entrar em contato com o “suporte” para tirar uma dúvida ou, quase sempre, reclamar.

Com os progressos da “Inteligência Artificial”, começaram a surgir agentes ou assistentes virtuais cujo objetivo principal é auxiliar as pessoas a navegar neste avassalador espaço virtual e encontrar o que se quer. E, em algum momento, os assistentes baseados em comandos de voz, como o Alexa e o Google Assistant se fundiram com as ferramentas de “chat”, como o WhatsApp e Telegram e os assistentes virtuais baseados em inteligência artificial para atender clientes de grandes empresas começaram a surgir “como cogumelos depois da chuva”! Os mais conhecidos por aqui são a “Joice“, da OI (detalhes); e a “Lu” do Magazine Luiza. Na prática, com essas ferramentas, os clientes falam com “robôs treinados” que são capazes de entender a pergunta – da mais vaga e imbecil até a mais precisa e inteligente – e responder de forma apropriada. E, como característica fundamental da Inteligência Artificial (Machine Learning), ficam a cada dia mais inteligentes.

Pois bem, essa “quarentena” e o “home office” tem dado algum tempo extra, não gasto no transporte público, para explorar algumas ferramentas novas e esses dias fui apresentado pelo meu sobrinho, Henrique Pinheiro, à ferramentas de reconhecimento de liguagem natural: O DialogFlow, do Google; e o Language Understanting, da Microsoft. Explorando o DialogFlow me veio a idéia de criar um assistente inteligente para atender “clientes” consumidores de informação sobre biodiversidade e conservação. Afinal, no Jardim Botânico do Rio de Janeiro somos bombardeados por perguntas sobre as plantas diariamente e seria interessante ter um agente, por exemplo, no WhatsApp, que pudesse responder perguntas destes clientes com rapidez e precisão, acessando nossos repositórios, recursos de informação e bases de dados.

Nestes exercícios, fico sempre na cabeça com um “personagem” que chamo de “Matheus”, em homenagem ao colega do Ministério do Meio Ambiente Matheus Marques Andreozzi, que me inspira mais do que ele imagina. Esse “Matheus” tem grande curiosidade sobre a flora e sempre liga ou manda email perguntando alguma coisa e acho que ele ficaria muito feliz em ter um contato no”WhatsApp”, disponível 24hs, para quem ele perguntaria coisas sobre a biodiversidade e conservação, e receberia respostas precisas, atuais e corretas.

Antes de prosseguir com o exercício, vale a pena entender melhor a motivação da ferramenta DialogFlow do Google: 

https://youtu.be/yT58gTXdQb8

Na exploração da ferramenta, consegui definir algumas entidades e “intenções” e cheguei a treinar a AI para simular “clientes” perguntando coisas como “Quais as espécies ameaçadas de Minas Gerais?”, “Quais as Unidades de Conservação tem espécies invasoras?”, “Carrapeta serve para dor de cabeça?”, “Qual o status de conservação do pau-brasil”, “Quantos gêneros de bromélias existem?”. Depois de algum treino a AI passou a entender intenção do cliente e identificar as entidades definidas préviamente, facilitando a criação de uma consulta estruturada à uma base de conhecimento ou mesmo uma base de dados, via SQL por exemplo.

Não pretendo entediar vocês com detalhes tecnicos nem me aprofundar demais pois, como sempre, as postagens que costumo fazer aqui são resultado de prospecção tecnológica e apontam para tecnologias com potencial para impactar a gestão e entrega da informação sobre biodiversidade.

Minha percepção é que a forma de consumir informação foi transformada de tal forma que, por exemplo, não é de se estranhar mais que em uma reunião alguém busque uma informação mais atualizada com um colega de trabalho pelo WhatsApp.

Consigo imaginar um cenário onde o “Matheus” está em uma reunião importante e o Secretário pergunta “Mas afinal, existem espécies criticamente ameaçadas no Parque Nacional da Chapada das Mesas?”. Neste momento ele saca o celular e manda uma mensagem para o Asssitente Virtual de Biodiversidade e Conservação e segundos depois vem a resposta: “Sim, e essa é a lista de espécies criticamente ameaçadas neste Parque…”.

É maravilhoso pensar que a tecnologia para isso está disponível HOJE.

UPDATE! Prova de conceito no ar:

https://youtu.be/rnvhvbzqOOE
