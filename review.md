# Redes

**O que são protocolos?**<br>
Protocolos são como um conjunto de ações/regras que se segue para fazer algo, como por exemplo, 
perguntas horas na rua à um desconhecido, o protocolo para isso seria você ao menos dizer oi ou com licença
antes de pedir a informação.<br>
Essa definição para computadores não muda muito, o protocolo vai definir a ordem e e o formato das mensagens
trocadas entre os componentes de hardware ou software, garantindo que possam se comunicar de maneira eficaz e efetiva
(exemplo: o HTTP que é responsável pela transmissão de dados em páginas web)
<br></br>
**Defina camada e interface. Quais as vantagens de usar esse método para se expressar em um projeto de redes**<br>
Camadas são divisões que tem em um modelo de arquitetura onde cada camada é responsável por uma fucionalidade, fornecendo esse serviço
à sua camada imediatamente superior, isolando os detalhes e passando apenas o produto final.<br>
Já interface, são os serviços oferecidos pela camada N a camada N+1. A vantagem de se utilizar este método é a 
divisão de um projeto complexo em áreas menores, relativamente independentes. Assim, a tecnologia que
implementa determinada camada pode ser alterada sem que com isto seja necessário
modificar a infraestrutura restante (outras camadas). Em uma analogia, a interface é a porta de cada comodo 
da casa, onde cada comodo é uma camada, se eu alterar o quarto, a sala não sofre alterações.
<br></br>
**Explique brevemente cada camada da arquitetura de redes passada em sala de aula, depois escolha uma e dê 3 exemplos**<br>
De cima pra baixo: <br>
Camada de aplicação
> A camada mais próxima do usuário, responsável por organizar dados em um padrão pro usuário. Exemplo: DNS, HTTP, SMTP
> Tradução de formatos para que aplicativos possam se comunicar em diferentes dispositivos (ex: windows e android)
> Gerencia sesões para que os dados sejam entregues na ordem correta
<br>

Camada de transporte
> Responsável pela transferencia de dados da camada de aplicação entre processos. Exemplo: TCP/UDP
> Garante a entrega confiável dos pacotes
> Divide os dados em segmentos
> Gerencia o fluxo de dados pra evitar sobrecarregar a rede
<br>

Camada de rede
> Responsável pela movimentação, de uma máquina pra outra, dos pacotes que são chamados de datagrama. Exemplo: Protocolo IP e Roteamento
> Define a melhor rota para caminhar os dados de origem para o destino
> Fragmenta pacotes grandes em pacotes menores para que cheguem rapidamente no destino
<br>

Camada de enlace
> Conecta roteadores e computadores, sendo o canal de comunicação. Se preocupa com 1 transmissão por vez, dos pacotes que aqui são chamados
de quadros. Exemplo: Ethernet, Wifi, Point to Point
> Controla quem acessa a mídia de transmissão
> Verifica e corrige erros nos quadros que estão sendo transmitidos
> Controla o fluxo dos pacotes
<br>

Camada física
> Tem como objetivo movimentar os bits individuais que estão dentro de um quadro de um ponto ao outro. Exemplo: Ethernet
> Modulação de sinais para que os bits trafeguem de forma apropriada pelo meio físico
> Converte dados digitais em sinais eletricos, ópticos ou de radiofrequencia

**Modelo de referência OSI**
> Dividido em sete camada/layers<br>
> Uma dada camada N requisita e utiliza serviços da camada anterior N–1.<br>
> É um modelo prático de padronização mantido pela ISO<br>

De cima pra baixo:
Aplicação
> a
Apresentação
> a
Sessão
> a
Transporte
> a
Redes
> a
Enlace
> a
Física
> a

**Cliente servidor**
O Cliente requisita um serviço ao servidor, este que possui um endereço ip fixo e fornece uma gama de
serviços. No entanto, se só possui um servidor e ele cair, não será possível acessar aos recursos nele oferecidos.
A vantagem é que tudo concentrado no mesmo local fica mais fácil de ser gerenciado<br>

**P2P**
No peer to peer, os pares podem atuar tanto como servidor, quanto cliente, não havendo uma distição bem definida entre eles. <br>
A vantagem é que se um cair, ainda há outro para executar o papel. Desvantagem é que acaba precisando de armazenamento e processamento potentes<br>

**HTTP**
Protocolo para transferencia de dados entre o servidor e o cliente web, normalmente a partir de um navegador. Existem dois tipos:
> HTTP Persistente: Uma única conexão pode ser usada para transferir vários recursos. Mais eficiente para carregar páginas web.<br>
> HTTP Não Persistente: Uma conexão é estabelecida entre o cliente e o servidor para cada recurso solicitado, depois é fechada. Exemplo: tem 5 imagens
numa página web, para cada iamgem tem que estabelecer uma conexão nova<br>

**Proxy WEB**
Atua como intermediario entre o cliente e o servidor web, todas as requisições passam pelo proxy e lá elas são filtradas (exemplo: não pode acessar tal conteudo,
o proxy barra) e tb ficam em cache, então quando solicitar dnv o proxy ve se teve alguma alteração, se não ele só manda direto sem ter que passar pro servidor<br>

**TCP**
orientado a conexão, para cada endereço ip ou porta é gerado uma nova conexão, o que é mais lento, mas pelo menos se o pacote chegar diferente a gente tem esse 
retorno de que deu errado. Também faz o controle de congestionamento/fluxo<br>

**UDP**
nao orientado a conexão, mais rapido pq usa uma socket só independente da porta de origem só que como desconhece a oriem ficamos sem saber se o 
datagrama chegou integro ou não<br>

**Checksum**
Soma tudo, pega o resultado soma com o inverso dele e tem que dar tudo 1. Lembrando: <br>
0 + 0 = 0, 1 + 0 = 1, 1 + 1= 0 e sobe 1
