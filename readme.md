# Socket TCP/IP
#### Autor do código: EDWARD MARTINS JR.
#### Origem: https://imasters.com.br/back-end/trabalhando-com-o-protocolo-tcpip-usando-go

Go é uma linguagem open source lançada, em 2009, pelo Google e criada por Robert Griesemer, Rob Pike e Ken Thompson.

Uma das coisas mais bacanas de Go é poder escrever código de forma simples, pouco verborrágica, estruturada e bastante eficaz, sem contar que é uma linguagem fortemente tipada, incrivelmente leve e suporta concorrência nativamente através de goroutines.

Dentre muitos pacotes, Go através do pacote “net” provê interfaces de acesso a I/O, incluindo a pilha TCP/IP, UDP, resolução por nome de domínio e UNIX Sockets.

Com uma ideia muito simples, neste artigo, iremos criar um cliente e um servidor TCP/IP que servirá para observarmos os principais aspectos destas implementações.

Para tal, vamos estabelecer um protocolo de comunicação bastante básico entre as duas aplicações para garantir que ambos, cliente e servidor, consigam executar suas tarefas.

### Servidor
O protocolo de comunicação que nosso servidor deverá trabalhar será este:

* Ouvir a interface tcp na porta 8081;
* Aceitar conexões;
* Dentro de um loop infinito, ouvir as mensagens a serem transmitidas pelo cliente;
* Escrever no terminal estas mensagens;
* Devolver a mensagem recebida ao cliente (eco).

### Cliente
O protocolo de comunicação que nosso cliente deverá trabalhar será este:

* Conectar-se a interface tcp localhost na porta 8081;
* Dentro de um loop infinito, realizar leitura do terminal;
* Escrever no socket a mensagem digitada no terminal (transmitir);
* Ouvir o retorno do servidor;
* Escrever no terminal a mensagen retornada (eco).

Para ter uma boa experiência deste exemplo, execute primeiramente o tcp-server e, em seguida, o tcp-client preferencialmente em terminais diferentes para acompanhar o resultado.
Obviamente existem tratamentos que devem ser realizados quanto a quebra de protocolo, exceções decorrentes do processamento das mensagens ou perda de conexão por uma das partes, mas… isso é com vocês!

Conclusão, Go é muito divertido!

Para ajudar, confira os links abaixo:

* Playground: https://play.golang.org/p/0by806NDWU
* Git: https://github.com/edwardmartinsjr/iMasters-Go/tree/master/tcp