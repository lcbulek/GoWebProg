
# Capítulo 1. Go e aplicações web

Este capítulo abrange

- Definindo aplicativos da web
- Usando Go para escrever aplicações web: as vantagens
- Compreendendo os fundamentos da programação de aplicativos da web
- Escrevendo o aplicativo web mais simples possível em Go

Os aplicativos da Web são onipresentes. Pegue qualquer aplicativo que você usa diariamente, e provavelmente é um aplicativo da Web ou tem uma variante de aplicativo da Web (isso inclui aplicativos móveis). Qualquer linguagem que suporte desenvolvimento de software que interage com seres humanos inevitavelmente suportará desenvolvimento de aplicativos da Web. Uma das primeiras coisas que os desenvolvedores de uma nova linguagem fazem é construir bibliotecas e estruturas para interagir com a Internet e a World Wide Web. Existem inúmeras ferramentas de desenvolvimento da Web para as linguagens mais estabelecidas.

Go não é diferente. Go é uma linguagem de programação relativamente nova, criada para ser simples e eficiente para escrever sistemas back-end. Ela tem um conjunto avançado de recursos e foca na eficácia e velocidade do programador. Desde seu lançamento, Go ganhou tremenda popularidade como uma linguagem de programação para escrever aplicativos da web e sistemas *-as-a-Service.

Neste capítulo, você aprenderá por que deve usar Go para escrever aplicativos web e aprenderá tudo sobre aplicativos web.

## 1.1. Usando Go para aplicações web

Então por que você deve usar Go para escrever aplicativos web? Meu palpite é que, tendo comprado este livro, você tem uma inclinação para descobrir a resposta. Claro, como autor de um livro que ensina programação web em Go, acredito que há razões fortes e convincentes para fazer isso. Conforme você continua lendo este livro, você terá uma noção dos pontos fortes de Go no desenvolvimento de aplicativos web e, espero, concordará comigo sobre a utilidade de Go.

Go é uma linguagem de programação relativamente nova, com uma comunidade próspera e crescente. É bem adequada para escrever programas do lado do servidor que sejam rápidos. É simples e familiar para a maioria dos programadores que estão acostumados com programação procedural, mas também fornece recursos de programação funcional. Ela suporta simultaneidade por padrão, tem um sistema de empacotamento moderno, faz coleta de lixo e tem um conjunto extenso e poderoso de bibliotecas padrão integradas.

Muitas bibliotecas de código aberto de boa qualidade estão disponíveis para suplementar o que as bibliotecas padrão não têm, mas as bibliotecas padrão que vêm com Go são bastante abrangentes e abrangentes. Este livro se apega às bibliotecas padrão tanto quanto possível, mas ocasionalmente usará bibliotecas de código aberto de terceiros para mostrar maneiras alternativas e criativas que a comunidade de código aberto criou.

Go está rapidamente ganhando popularidade como uma linguagem de desenvolvimento web. Muitas empresas, incluindo empresas de infraestrutura como Dropbox e SendGrid, empresas voltadas para tecnologia como Square e Hailo, bem como empresas mais tradicionais como BBC e The New York Times, já começaram a usar Go.

Go fornece uma alternativa viável às linguagens e plataformas existentes para o desenvolvimento de aplicativos da web em larga escala. Os aplicativos da web em larga escala geralmente precisam ser

- Escalável
- Modular
- Sustentável
- Alto desempenho

Vamos dar uma olhada nesses atributos em detalhes.

### 1.1.1. Aplicações web escaláveis ​​e Go

Os aplicativos da web em larga escala devem ser escaláveis . Isso significa que você deve ser capaz de aumentar rápida e facilmente a capacidade do aplicativo para assumir um volume maior de solicitações. O aplicativo também deve ser escalável linearmente, o que significa que você deve ser capaz de adicionar mais hardware e processar um número correspondente de solicitações.

Podemos analisar a escala de duas maneiras:

- Escala vertical , ou aumento da quantidade de CPUs ou capacidade em uma única máquina
- Escala horizontal , ou aumento do número de máquinas para expandir a capacidade

Go escala bem verticalmente com seu excelente suporte para programação simultânea. Um único aplicativo web Go com um único thread de SO pode ser programado para executar centenas de milhares de goroutines com eficiência e desempenho.

Assim como qualquer outro aplicativo da web, o Go pode escalar bem horizontalmente, bem como por camadas de um proxy sobre um número de instâncias de um aplicativo da web Go. Os aplicativos da web Go são compilados como binários estáticos, sem nenhuma dependência dinâmica, e podem ser distribuídos para sistemas que não têm Go integrado. Isso permite que você implante aplicativos da web Go de forma fácil e consistente.

### 1.1.2. Aplicações web modulares e Go

Os aplicativos da web em larga escala devem ser construídos com componentes que funcionam de forma intercambiável. Essa abordagem permite que você adicione, remova ou modifique recursos facilmente e lhe dá a flexibilidade para atender às necessidades de mudança do aplicativo. Ela também permite que você reduza os custos de desenvolvimento de software reutilizando componentes modulares.

Embora Go seja estaticamente tipado, ele tem um mecanismo de interface que descreve o comportamento e permite tipagem dinâmica. Funções podem receber interfaces, o que significa que você pode introduzir um novo código no sistema e ainda ser capaz de usar funções existentes implementando métodos requeridos por essa interface. Além disso, com uma função que recebe uma interface vazia, você pode colocar qualquer valor como parâmetro porque todos os tipos implementam a interface vazia. Go implementa uma série de recursos geralmente associados à programação funcional, incluindo tipos de função, funções como valores e fechamentos. Esses recursos permitem que você crie um código mais modular, fornecendo a capacidade de criar funções a partir de outras funções.

Go também é frequentemente usado para criar microsserviços . Na arquitetura de microsserviços, aplicativos de larga escala podem ser criados compondo serviços independentes menores. Esses serviços são intercambiáveis ​​e organizados em torno de recursos (por exemplo, um serviço de nível de sistema como registro ou um serviço de nível de aplicativo como faturamento ou análise de risco). Ao criar vários serviços Go pequenos e compô-los em um único aplicativo da web, você permite que esses recursos sejam intercambiáveis ​​e, portanto, mais modulares.

### 1.1.3. Aplicações web sustentáveis ​​e Go

Como qualquer aplicativo grande e complexo, ter uma base de código facilmente sustentável é importante para aplicativos web de larga escala. É importante porque aplicativos de larga escala geralmente precisam crescer e evoluir e, portanto, você precisa revisitar e alterar o código regularmente. Código complexo e difícil de manejar leva muito tempo para mudar e está repleto de risco de algo quebrar, então faz sentido manter o código-fonte bem organizado e sustentável.

Go foi projetado para encorajar boas práticas de engenharia de software. Ele tem uma sintaxe limpa e simples que é muito legível. O sistema de pacotes do Go é flexível e inequívoco, e há um bom conjunto de ferramentas para aprimorar a experiência de desenvolvimento e ajudar os programadores a escrever códigos mais legíveis. Um exemplo é o formatador de código-fonte Go ( gofmt ) que padroniza a formatação do código Go.

O Go espera que a documentação evolua junto com o código. A ferramenta de documentação do Go ( godoc ) analisa o código-fonte do Go, incluindo comentários, e cria documentação em uma variedade de formatos, como HTML e texto simples. É muito fácil de usar — ​​basta escrever a documentação acima do próprio código-fonte e o godoc a extrairá junto com o código para gerar a documentação.

O teste é integrado ao Go. O gotest descobre casos de teste integrados no mesmo pacote e executa testes funcionais e de desempenho. O Go também fornece ferramentas de teste de aplicativos da web emulando um cliente da web e gravando respostas geradas pelo servidor.

### 1.1.4. Aplicações web de alto desempenho e Go

Alto desempenho significa ser capaz de processar um grande volume de solicitações em um curto período de tempo. Também significa ser capaz de responder ao cliente rapidamente e tornar as operações mais rápidas para os usuários finais.

Um dos objetivos de design do Go é se aproximar do desempenho do C e, embora não tenha atingido esse objetivo, os resultados atuais são bastante competitivos. O Go compila para código nativo, o que geralmente significa que é mais rápido do que outras linguagens e frameworks interpretados. Conforme descrito anteriormente, o Go também tem ótimo suporte de simultaneidade com goroutines, o que permite que várias solicitações sejam processadas ao mesmo tempo.

Espero ter convencido você de que Go vale pelo menos a pena ser pesquisado como uma linguagem e plataforma útil para desenvolver aplicativos web. Mas antes de pularmos para qualquer código Go, vamos entrar em sincronia sobre o que são aplicativos web e como eles funcionam. Isso será importante conforme você ler os próximos capítulos.

## 1.2. Como funcionam os aplicativos da web

Pergunte a uma sala cheia de programadores o que é um aplicativo da web e você provavelmente obterá uma ampla gama de respostas (além de olhares de desprezo e espanto por fazer uma pergunta tão básica). Mas, conforme você obtém suas respostas dos tecnólogos reunidos, você pode perceber que o entendimento comum do que é um aplicativo da web pode não ser tão direto. Por exemplo, um serviço da web também é um aplicativo da web? Muitos os considerariam diferentes, principalmente porque os serviços da web são consumidos por outros softwares, enquanto os aplicativos da web são usados ​​por humanos. Mas se um aplicativo da web produz dados que são legíveis por humanos, mas são consumidos apenas por outros softwares (como com um feed RSS), ele é um serviço da web ou ainda um aplicativo da web?

Se um aplicativo retorna apenas uma página HTML sem nenhum processamento, ele é um aplicativo da web? Um programa Adobe Flash em execução em um navegador da web é um aplicativo da web? Que tal um aplicativo escrito apenas em HTML5, em execução no seu navegador, mas que reside no seu laptop? Se o aplicativo não usa HTTP para enviar solicitações a um servidor, ele ainda é um aplicativo da web? Em um nível mais alto, a maioria dos programadores entende o que é um aplicativo da web. Em um nível mais baixo, de implementação, no entanto, as coisas ficam confusas e cinzentas.

Em um sentido purista e restrito, um aplicativo web é um programa de computador que responde a uma solicitação HTTP de um cliente e envia HTML de volta ao cliente em uma resposta HTTP. Mas não é isso que um servidor web é? A partir dessa definição, não há diferença entre um servidor web e um aplicativo web. O servidor web é o aplicativo web (veja a figura 1.1 ).

Figura 1.1. Estrutura básica de solicitação e resposta de um aplicativo da web

![alt text](00151.jpg)

A única consideração é provavelmente que um servidor web como httpd ou Apacheolha para um diretório específico (no Apache, este é o docroot ) e retorna arquivos naquele diretório quando solicitado. Em comparação, um aplicativo web não retorna simplesmente arquivos; ele processa a solicitação e executa operações que são programadas no aplicativo (veja a figura 1.2 ).

Figura 1.2. Como funciona uma aplicação web

![alt text](00162.jpg)

Deste ponto de vista, você provavelmente pode considerar um servidor web como um tipo especializado de aplicativo web que retorna apenas arquivos que estão sendo solicitados. Em um sentido mais amplo, muitos usuários considerariam qualquer aplicativo que usa um navegador como cliente como um aplicativo web. Isso inclui aplicativos Adobe Flash, aplicativos web de página única e até mesmo aplicativos que não são servidos por HTTP, mas que residem em seu desktop ou laptop.

No contexto deste livro, precisamos traçar a linha em algum lugar. Vamos considerar primeiro o que é um aplicativo .

Um aplicativo é um programa de software que interage com um usuário e o ajuda a executar uma atividade. Isso inclui sistemas de contabilidade, sistemas de recursos humanos, software de publicação de desktop e assim por diante. Um aplicativo da web é, então, um aplicativo que é implantado e usado pela web.

Em outras palavras, um programa precisa atender apenas dois critérios para ser considerado um aplicativo web:

- O programa deve retornar HTML para um cliente que faz a chamada, que renderiza o HTML e o exibe para um usuário.
- Os dados devem ser transportados para o cliente via HTTP.

Como uma extensão desta definição, se um programa não renderiza HTML para um usuário, mas em vez disso retorna dados em qualquer outro formato para outro programa, ele é um serviço web (ou seja, ele fornece um serviço para outros programas). Entraremos em serviços web no capítulo 7 .

Embora esta seja provavelmente uma definição mais restrita do que a que a maioria dos programadores provavelmente definiria como um aplicativo da web, é útil para nossa discussão neste livro. Ela elimina toda a imprecisão e torna os aplicativos da web muito mais fáceis de entender. À medida que progredimos, as coisas começarão a fazer muito mais sentido. Mas primeiro, vamos entender como o HTTP veio a ser do jeito que é hoje.

## 1.3. Uma rápida introdução ao HTTP

HTTP é o protocolo de comunicações em nível de aplicativo que alimenta a World Wide Web. Tudo o que você vê em uma página da web é transportado por meio desse protocolo aparentemente simples baseado em texto. HTTP é simples, mas surpreendentemente poderoso — desde sua definição em 1990, ele passou por apenas três mudanças iterativas. HTTP 1.1 é a versão mais recente, e HTTP 2.0 está em forma de rascunho.

A primeira versão do HTTP (HTTP 0.9), criada por Tim Berners-Lee, era um protocolo simples criado para ajudar na adoção da World Wide Web. Ele permite que um cliente abra uma conexão com um servidor, emita uma solicitação de sequência de caracteres ASCII e termine com um retorno de carro (CRLF). O servidor então responde apenas com o HTML (nenhum outro metadado).

A explosão de recursos veio com diferentes implementações do HTTP. Eventualmente, a multidão de recursos consolidou-se como HTTP 1.0 em 1996, seguido pelo HTTP 1.1 em 1999, que é a versão mais comum em uso hoje. O HTTP 2.0 (ou HTTP/2) está em rascunho, então neste livro nos concentraremos apenas no HTTP 1.1.

Vamos começar definindo o que é HTTP primeiro (esta é minha definição simplificada):

**HTTP**

HTTP é um protocolo de solicitação-resposta, sem estado e baseado em texto, que usa o modelo de computação cliente-servidor.

Solicitação-resposta é uma maneira básica de dois computadores se comunicarem. O primeiro computador envia uma solicitação ao segundo computador e o segundo computador responde a essa solicitação. Um modelo de computação cliente-servidor é aquele em que o solicitante (o cliente ) sempre inicia a conversa com o respondente (o servidor ). Como o nome sugere, o servidor fornece um serviço ao cliente. Em HTTP, o cliente também é conhecido como agente do usuário e geralmente é um navegador da web. O servidor geralmente é chamado de servidor da web .

HTTP é um protocolo sem estado. Cada solicitação do cliente para o servidor retorna uma resposta do servidor para o cliente, e isso é tudo que o protocolo lembra. Solicitações subsequentes para o mesmo servidor não têm absolutamente nenhuma ideia do que aconteceu antes. Em comparação, protocolos orientados a conexão como FTP ou Telnet (também solicitação-resposta e cliente-servidor) criam um canal persistente entre o cliente e o servidor. Dito isso, o HTTP 1.1 persiste conexões para melhorar o desempenho.

O HTTP envia e recebe dados relacionados ao protocolo em texto simples (ao contrário do envio e recebimento em binário), como muitos outros protocolos relacionados à internet. A lógica por trás disso é permitir que você veja o que acontece com as comunicações sem um analisador de protocolo especializado, tornando a solução de problemas muito mais fácil.

O HTTP foi originalmente projetado para entregar somente HTML e o HTTP 0.9 tinha apenas um método: GET. Versões posteriores o expandiram para ser um protocolo genérico para sistemas colaborativos distribuídos, incluindo aplicativos da web, que abordaremos a seguir.

## 1.4. A chegada das aplicações web

Pouco tempo depois que a World Wide Web foi apresentada ao mundo em geral, as pessoas começaram a perceber que apenas servir arquivos é ótimo, mas seria ainda melhor se o conteúdoservido foi criado dinamicamente. Uma das primeiras tentativas de fazer isso foi a Common Gateway Interface (CGI).

Em 1993, o National Center for Supercomputing Applications (NCSA) escreveu uma especificação para chamar programas executáveis ​​de linha de comando chamados CGI. O NCSA incluiu isso em seu popular NCSA httpd . Apesar do nome, ele nunca se tornou um padrão de internet.

CGI é uma interface simples que permite que um servidor web faça interface com um programa que está sendo executado separadamente e externamente ao processo do servidor web. Este programa, geralmente chamado de programa CGI, pode ser escrito em qualquer linguagem (daí, common ), e nos primeiros anos era principalmente Perl. A entrada para o programa CGI é feita por meio de variáveis ​​de ambiente, e qualquer coisa que o programa CGI produza na saída padrão é retornada ao cliente por meio do servidor.

Outra tecnologia do mesmo período é server-side includes (SSI), que são diretivas que você pode incluir em um arquivo HTML. Essas diretivas são executadas quando o arquivo HTML é solicitado e o conteúdo da execução dessas diretivas é incluído no local onde a diretiva estava, antes que o conteúdo final seja entregue ao cliente. Um dos usos mais populares do SSI é incluir um arquivo usado com frequência em outro, ou incorporar snippets de cabeçalho e rodapé que são comuns em todo o site.

Como exemplo, o código a seguir inclui o conteúdo do arquivo navbar.shtml no local onde você colocou a diretiva:

```html
<html>
    <head><title>Exemplo de SSI</title></head>
    <body><!--#include file="navbar.shtml" --></body> 
</html>
```

A evolução eventual do SSI foi incluir código mais complexo no HTML e usar intérpretes mais poderosos. Esse padrão cresceu em mecanismos de grande sucesso para construir aplicativos web sofisticados, como PHP, ASP, JSP e ColdFusion. Isso também se tornou a base para mecanismos de template web, como Mustache, ERB, Velocity e muitos outros.

Como você pode ver, os aplicativos da web se originaram como entrega de conteúdo personalizado e dinâmico ao usuário por meio de HTTP. Para descobrir como os aplicativos da web operam, você precisa saber como o HTTP funciona e entender as solicitações e respostas HTTP.

## 1.5. Solicitação HTTP

HTTP é um protocolo de solicitação-resposta, então tudo começa com uma solicitação. A solicitação HTTP, como qualquer mensagem HTTP, consiste em algumas linhas de texto na seguinte ordem:

1. Linha de solicitação
2. Zero ou mais cabeçalhos de solicitação
3. Uma linha vazia
4. O corpo da mensagem (opcional)

Esta é a aparência de uma solicitação HTTP típica:

    GET /Protocols/rfc2616/rfc2616.html HTTP/1.1
    Host: <www.w3.org>
    User-Agent: Mozilla/5.0
    (linha em branco)

Nesta solicitação, a primeira linha é a request-line :

    GET /Protocols/rfc2616/rfc2616.html HTTP/1.1

A primeira palavra na linha de solicitação é o método de solicitação , seguido pelo Uniform Resource Identifier (URI) e a versão do HTTP a ser usada. As próximas duas linhas são os cabeçalhos de solicitação . Observe que a última linha é uma linha vazia, que deve existir mesmo que não haja corpo de mensagem. Se o corpo da mensagem existe ou não depende do método de solicitação.

### 1.5.1. Métodos de solicitação

O método de solicitação é a primeira palavra na linha de solicitação e indica a ação a ser feita no recurso. O HTTP 0.9 tinha apenas um método: GET. O HTTP 1.0 adicionou POST e HEAD. O HTTP 1.1 adicionou outros cinco — PUT, DELETE, OPTIONS, TRACE e CONNECT — e abriu a possibilidade de adicionar mais métodos (e muitos o fizeram prontamente).

Curiosamente, o HTTP 1.1 especifica que GET e HEAD devem sempre ser implementados, enquanto todos os outros métodos são opcionais (isso significa que até POST é opcional).

**GET** - Diz ao servidor para retornar o recurso especificado.

**HEAD** - O mesmo que GET, exceto que o servidor não deve retornar um corpo de mensagem. Este método é frequentemente usado para obter os cabeçalhos de resposta sem carregar o peso do resto do corpo da mensagem pela rede.

**POST** - Diz ao servidor que os dados no corpo da mensagem devem ser passados ​​para o recurso identificado pelo URI. O que o servidor faz com o corpo da mensagem é decisão do servidor.

**PUT** - Diz ao servidor que os dados no corpo da mensagem devem ser o recurso no URI fornecido. Se os dados já existirem no recurso identificado pelo URI, esses dados serão substituídos. Caso contrário, um novo recurso será criado no local onde o URI está.

**DELETE** -  Diz ao servidor para remover o recurso identificado pelo URI.

**TRACE** - Diz ao servidor para retornar a solicitação. Dessa forma, o cliente pode ver o que os servidores intermediários fizeram com a solicitação.

**OPÇÕES** -  Diz ao servidor para retornar uma lista de métodos HTTP suportados pelo servidor.

**CONNECT** - Diz ao servidor para configurar uma conexão de rede com o cliente. Este método é usado principalmente para configurar o tunelamento SSL (para habilitar HTTPS).

**PATCH** - Informa ao servidor que os dados no corpo da mensagem modificam o recurso identificado pelo URI.

### 1.5.2. Métodos de solicitação seguros

Um método é considerado seguro se não altera o estado do servidor — ou seja, o servidor fornece apenas informações e nada mais. GET, HEAD, OPTIONS e TRACE são métodos seguros porque não devem alterar nada no servidor. Em comparação, os métodos POST, PUT e DELETE alteram o estado do servidor; por exemplo, após uma solicitação POST ser enviada, os dados no servidor devem ser alterados.

### 1.5.3. Métodos de solicitação idempotentes

Um método é considerado idempotente se o estado do servidor não muda na segunda vez que o método é chamado com os mesmos dados. Métodos seguros por definição também são considerados idempotentes (embora, obviamente, não o contrário).

PUT e DELETE são idempotentes, mas não são seguros. Isso ocorre porque PUT e DELETE não alteram o estado do servidor na segunda vez em que são chamados. PUT com o mesmo recurso resultará nas mesmas ações sendo tomadas pelo servidor, porque após a primeira solicitação, o recurso no URI já está atualizado ou criado. DELETE com o mesmo recurso pode resultar em um erro pelo servidor, mas o estado não muda.

POST não é um método seguro nem idempotente porque solicitações POST subsequentes ao servidor podem (ou não) resultar em uma mudança de estado, dependendo do servidor. Idempotência é uma ideia importante que revisitaremos quando falarmos sobre serviços web no capítulo 7 .

### 1.5.4. Suporte do navegador para métodos de solicitação

GET é o método HTTP mais fundamental, e é suportado por todos os navegadores porque é como você realmente obtém conteúdo do servidor. O suporte a POST começou com o HTML 2.0 com a adição de formulários HTML. A tag de formulário HTML tem um atributo, method , que aceita o valor get ou post que indica qual método HTTP você deseja usar.

O HTML não suporta nenhum outro método HTTP além de GET e POST. Nos primeiros rascunhos do HTML5, o suporte a PUT e DELETE foi adicionado como valores no atributo do método do formulário HTML , mas foi retirado novamente.

Os navegadores modernos fazem mais do que apenas HTML, no entanto. Para dar suporte a PUT e DELETE, você pode usar XMLHttpRequest (XHR). XHR é um conjunto de APIs de navegador (na verdade, é basicamente apenas um objeto de navegador chamado XMLHttpRequest) com código JavaScript geralmente envolvido nele. XHR permite que os programadores enviem solicitações HTTP para o servidor e, apesar do nome, não se limita a usar apenas XML. Solicitações e respostas podem ser enviadas em qualquer formato, incluindo JSON e arquivos de texto.

### 1.5.5. Cabeçalhos de solicitação

Embora o método de solicitação HTTP defina a ação solicitada pelo cliente que faz a chamada, outras informações sobre a solicitação ou o cliente são frequentemente colocadas em cabeçalhos de solicitação HTTP. Os cabeçalhos de solicitação são pares nome-valor separados por dois pontos em texto simples, terminados por um retorno de carro (CR) e uma quebra de linha (LF).

Um conjunto central de campos de solicitação HTTP é padronizado no RFC 7231 (que é parte do conjunto de RFCs HTTP 1.1). No passado, campos de solicitação HTTP não padronizados começavam convencionalmente com X- , mas essa prática foi descontinuada.

Os cabeçalhos de solicitação HTTP são, em sua maioria, opcionais. O único cabeçalho obrigatório no HTTP 1.1 é o campo de cabeçalho Host. Mas se a mensagem tiver um corpo de mensagem (que é opcional, dependendo do método), você precisará ter os campos de cabeçalho Content-Length ou Transfer-Encoding. Alguns cabeçalhos de solicitação comuns que você verá aparecerem na tabela 1.1 .

Tabela 1.1. Cabeçalhos comuns de solicitação HTTP 

- Accept: Tipos de conteúdo que são aceitáveis ​​pelo cliente como parte da resposta HTTP. Por exemplo, Accept: text/html sinaliza ao servidor que o cliente quer que o tipo de conteúdo do corpo da resposta esteja em HTML.
- Accept-Charset: Os conjuntos de caracteres requeridos do servidor. Por exemplo, Accept-Charset: utf-8 informa ao servidor que o cliente quer que o corpo da resposta esteja em UTF-8.
Autorização Isso é usado para enviar credenciais de autenticação básica para o servidor.
- Autorization Cookie: O cliente deve enviar de volta os cookies que foram definidos pelo servidor de chamada. Se o servidor tiver definido três cookies no navegador anteriormente, o campo de cabeçalho Cookie conterá todos os três cookies em uma string de par nome-valor delimitada por ponto e vírgula. Por exemplo: Cookie: my_first_cookie=hello; my_second_cookie=world
- Content-Length: O comprimento do corpo da solicitação em octetos.
- Content-Type: O tipo de conteúdo do corpo da solicitação (quando há um corpo de solicitação). - Quando um POST ou um PUT é enviado, o tipo de conteúdo é por padrão x-www-form-urlencoded. Mas ao carregar um arquivo (usando a tag HTML input com o atributo type definido como file, ou de outra forma), o tipo de conteúdo deve ser multipart/form-data.
- Host: O nome do servidor, junto com o número da porta. Se o número da porta for omitido, ele será resolvido como porta 80.
- Referer: O endereço da página anterior que continha um link para a página solicitada.
- User Agent:  Descreve o cliente que efetua a chamada.

## 1.6. Resposta HTTP

Uma mensagem de resposta HTTP é enviada toda vez que há uma solicitação. Assim como a solicitação HTTP, a resposta HTTP consiste em algumas linhas de texto simples:

- Uma linha de status
- Zero ou mais cabeçalhos de resposta
- Uma linha vazia
- O corpo da mensagem (opcional)

Você provavelmente percebeu que uma resposta HTTP é estruturada da mesma forma que uma solicitação HTTP. É assim que uma resposta HTTP típica se parece (abreviada para salvar árvores):

    200 OK
    Date: Sat, 22 Nov 2014 12:58:58 GMT
    Server: Apache/2
      Last-Modified: Thu, 28 Aug 2014 21:01:33 GMT
    Content-Length: 33115
    Content-Type: text/html; charset=iso-8859-1

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/
         TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns='http://www.w3.org/1999/
         xhtml'> <head><title>Hypertext Transfer Protocol -- HTTP/1.1</title></
         head><body>...</body></html>

A primeira linha da resposta HTTP é a linha de status , que consiste no código de status e uma frase de razão correspondente , que é uma breve descrição do código. Neste caso, a resposta HTTP tem um corpo de mensagem, que está em HTML.

### 1.6.1. Código de status de resposta

Conforme mencionado anteriormente, o código de status em uma resposta HTTP indica que tipo de resposta é. Há cinco classes de códigos de status de resposta HTTP, dependendo do primeiro dígito do código (veja a tabela 1.2 ).

Tabela 1.2. Códigos de status de resposta HTTP

**1XX** Informativo. Isso informa ao cliente que o servidor já recebeu a solicitação e está processando-a.

**2XX** Sucesso. É isso que os clientes querem; o servidor recebeu a solicitação e a processou com sucesso. A resposta padrão nesta classe é 200 OK.

**3XX** Redirecionamento. Isso informa ao cliente que a solicitação foi recebida e processada, mas o cliente precisa fazer mais para concluir a ação. A maioria dos códigos de status nesta classe são para redirecionamento de URL.

**4XX** Erro do cliente. Isso informa ao cliente que há algo errado com a solicitação. O status mais conhecido nessa classe é 404 Not Found, em que o servidor informa ao cliente que o recurso que ele está tentando obter não foi encontrado naquele URL.

**5XX** Erro do Servidor. Isso informa ao cliente que há algo errado com a solicitação, mas é culpa do servidor. O código de status genérico nessa classe é 500 Internal Server Error.

### 1.6.2. Cabeçalhos de resposta

Os cabeçalhos de resposta são semelhantes aos cabeçalhos de solicitação. Ambos são pares nome-valor separados por dois pontos em texto simples, terminados por um CR e LF. Assim como a solicitaçãocabeçalhos dizem ao servidor mais sobre a solicitação e o que o cliente quer, os cabeçalhos de resposta são os meios para o servidor dizer ao cliente mais sobre a resposta e o que o servidor quer (do cliente). Alguns cabeçalhos de resposta comumente usados ​​são mostrados na tabela 1.3 .

Tabela 1.3. Cabeçalhos de resposta comuns

- Allow: Informa ao cliente quais métodos de solicitação são suportados pelo servidor.
- Content-Length: O comprimento do corpo da resposta em octetos (bytes de 8 bits).
- Content-Type: O tipo de conteúdo do corpo da resposta (quando há um corpo de resposta).
- Date: Informa a hora atual (formatada em GMT).
- Location: Este cabeçalho é usado com redirecionamento, para informar ao cliente onde solicitar o próximo URL.
- Server: Nome de domínio do servidor que está retornando a resposta.
Set-Cookie: Define um cookie no cliente. Vários cabeçalhos Set-Cookie podem ser adicionados à mesma resposta.
- WWW-Autenticate: Informa ao cabeçalho do cliente qual tipo de autorização os clientes devem fornecer em seu cabeçalho de solicitação de Autorização. O servidor geralmente envia isso junto com uma linha de status 401 Unauthorized. Este cabeçalho também fornece as informações de desafio para os esquemas de autenticação que são aceitos pelo servidor (por exemplo, os esquemas de autenticação de acesso básico e digest descritos no RFC 2617).

## 1.7. URI

Quando Tim Berners-Lee apresentou a World Wide Web ao mundo, ele também apresentou a ideia de uma sequência de caracteres de localização representando um recurso na internet. Em junho de 1994, Berners-Lee publicou o RFC 1630, que definiu o URI. Nele, ele descreveu os conceitos de uma sequência de caracteres que representa o nome do recurso ( uniform resource name , ou URN) e uma sequência de caracteres que representa a localização do recurso ( uniform resource locator , ou URL). O URI é um termo abrangente que inclui tanto o URN quanto o URI, e eles têm sintaxe e formato semelhantes. Este livro usa apenas URLs, então, para todos os propósitos, tanto o URI quanto o URL podem ser usados ​​de forma intercambiável.

Esta é a forma geral de um URI: <nome do esquema> : <parte hierárquica> [ ? <consulta> ] [ # <fragmento> ]

O nome do esquema é o nome do esquema URI que define o resto da estrutura URI. Um grande número de esquemas URI está em uso, porque URI é uma maneira popular de identificar recursos. Mas o que usaremos mais neste livro é o esquema HTTP.

A parte hierárquica contém as informações de identificação e deve ser hierárquica em estrutura. Se a parte hierárquica começar com uma barra dupla (//), então ela serácontém informações opcionais do usuário que terminam com @ , seguido pelo caminho hierárquico. Caso contrário, é apenas o caminho. O caminho é uma sequência de segmentos, separados por uma barra (/).

Somente o nome do esquema e as partes hierárquicas são obrigatórias. A consulta , que começa com um ponto de interrogação (?), é opcional e contém outras informações que não são hierárquicas por natureza. A consulta é frequentemente organizada como uma sequência de pares de chave-valor, separados por um e comercial (&).

Outra parte opcional é o fragmento , que é um identificador para um recurso secundário que faz parte do URI que é definido. O fragmento começa depois do hash (#). Se um URI tiver uma consulta, o fragmento seguirá a consulta. O fragmento deve ser processado pelo cliente, então os navegadores da web normalmente retiram o fragmento antes de enviar o URI para o servidor. Mas isso não significa que, como programador, você não obterá o fragmento; você sempre pode incluí-lo em uma solicitação GET por meio de JavaScript ou algumas bibliotecas de cliente HTTP.

Vejamos um exemplo de um esquema HTTP URI: <http://sausheong:password@www.example.com/docs/file?name=sausheong&location=singapore#summary>

O esquema é http , seguido por dois pontos. O segmento sausheong:password seguido pelo sinal de arroba ( @ ) são as informações de usuário e senha. Isso é seguido pelo restante da parte hierárquica, <www.example.com/docs/file> . O nível superior da parte hierárquica é o nome de domínio do servidor, <www.example.com> , seguido por docs e depois file , cada um separado por uma barra. A seguir está a consulta, que começa após o ponto de interrogação ( ? ). A consulta consiste em dois pares nome-valor: name=sausheong e location=singapore , unidos por um único e comercial ( & ). Finalmente, o fragmento segue após a consulta, começando após o hash ( # ).

A URL é uma única string, então espaços dentro da URL não são permitidos. Além disso, certos caracteres como o ponto de interrogação (?) e o hash (#) têm significado especial dentro da URL e, portanto, não podem ser permitidos para outros propósitos. Para superar essa limitação, usamos codificação de URL (também chamada de codificação percentual) para converter esses caracteres especiais em outra coisa.

O RFC 3986 define um conjunto de caracteres que são reservados ou não reservados. Tudo na lista reservada precisa ser codificado em URL. A codificação de URL codifica um caractere convertendo-o em seu valor de byte correspondente em ASCII, representando-o como um par de dígitos hexadecimais e acrescentando-lhe um sinal de porcentagem (%).

Por exemplo, o valor de byte de um espaço em branco em ASCII é 32, que é 20 em hexadecimal. Portanto, a codificação de URL de um espaço é %20 , e isso é usado em uma URL em vez de um espaço. Este exemplo mostra a URL se eu tivesse usado meu nome com o espaço entre sau e sheong: <http://www.example.com/docs/file?name=sau%20sheong&location=singapore> .

## 1.8. Introdução ao HTTP/2

HTTP/2, a nova versão do HTTP, foca no desempenho. O HTTP/2 é baseado no SPDY/2, um protocolo de rede aberto desenvolvido principalmente no Google para transportar conteúdo da web, embora ao longo do tempo tenha havido uma série de mudanças.

HTTP/2 é um protocolo binário, diferente do HTTP/1.x, que é baseado em texto. Isso torna o HTTP/2 mais eficiente para analisar, e é mais compacto e menos propenso a erros. Mas isso significa que você não pode mais enviar mensagens HTTP/2 diretamente pela rede, por meio de aplicativos como telnet, e por isso é mais difícil de depurar se você estiver acostumado com HTTP/1.x.

Ao contrário do HTTP/1.x, que permite apenas uma única solicitação em uma conexão por vez, o HTTP/2 é totalmente multiplexado. Isso significa que várias solicitações e respostas podem estar usando a mesma conexão ao mesmo tempo. O HTTP/2 também compacta o cabeçalho para reduzir a sobrecarga e permite que o servidor envie respostas para o cliente, melhorando o desempenho em geral.

Como você pode ver, o HTTP/2 geralmente melhora o desempenho de comunicações do protocolo. O que não é alterado é a semântica do HTTP; por exemplo, os métodos HTTP, códigos de status e assim por diante. Isso ocorre porque o HTTP é tão amplamente usado, e qualquer alteração na semântica quebraria a web existente.

No Go 1.6, se você estiver usando HTTPS, você estará automaticamente usando HTTP/2. Para versões anteriores do Go, o pacote golang.org/x/net/http2 implementa o protocolo HTTP/2. Você verá como ele pode ser usado no capítulo 3 .

## 1.9. Partes de um aplicativo da web 

Nas seções anteriores, você viu que um aplicativo web é um pedaço de programa que faz o seguinte:

1. Recebe a entrada via HTTP do cliente na forma de uma mensagem de solicitação HTTP
2. Processa a mensagem de solicitação HTTP e executa o trabalho necessário
3. Gera HTML e o retorna em uma mensagem de resposta HTTP
Como resultado, há duas partes distintas de um aplicativo web: os manipuladores e o mecanismo de modelo .

### 1.9.1. Manipulador

Um manipulador recebe e processa a solicitação HTTP enviada do cliente. Ele também chama o mecanismo de template para gerar o HTML e, finalmente, agrupa os dados na resposta HTTP para serem enviados de volta ao cliente.

No padrão MVC, o manipulador é o controlador, mas também o modelo. Em uma implementação ideal do padrão MVC, o controlador seria fino, com apenas roteamento e lógica de desempacotamento e empacotamento de mensagens HTTP. Os modelos são gordos, contendo a lógica e os dados do aplicativo.

**Padrão Model-View-Controller**

O padrão Model-View-Controller (MVC) é um padrão popular para escrever aplicativos web, tão popular que às vezes é confundido com o próprio modelo de desenvolvimento de aplicativos web.

O MVC foi introduzido no Smalltalk no final da década de 1970 (mais de 10 anos antes da World Wide Web e do HTTP) no Xerox PARC. O padrão MVC divide um programa em três partes: modelo, visualização e controlador. O modelo é uma representação dos dados subjacentes, a visualização é uma visualização do modelo para o usuário e o controlador usa a entrada do usuário para modificar o modelo. Quando o modelo muda, a visualização é atualizada automaticamente para mostrar a visualização mais recente.

Embora originalmente desenvolvido para desktop, ele se tornou popular para escrever aplicativos da web, e muitas estruturas de aplicativos da web — incluindo Ruby on Rails, CodeIgniter, Play e Spring MVC — o usam como seu padrão de base. O modelo é frequentemente mapeado para um banco de dados usando estruturas ou objetos, as visualizações são o HTML retornado, e os controladores roteiam as solicitações e gerenciam o acesso aos modelos.

Muitos programadores novatos que constroem seus aplicativos web com frameworks de aplicativos web baseados em MVC frequentemente confundem o padrão MVC como a única maneira de desenvolver aplicativos web. Na verdade, aplicativos web são simplesmente aplicativos que interagem com usuários pelo protocolo HTTP, e qualquer padrão (ou nenhum padrão) que permita que tais aplicativos sejam escritos pode ser usado.

Às vezes, objetos de serviço ou funções são usados ​​para manipular os modelos, livrando o modelo de ser muito inchado e permitindo a reutilização do código. Nesse caso, objetos de serviço podem ser reutilizados em modelos diferentes e a mesma lógica pode ser colocada em um único objeto de serviço em vez de ser copiada em modelos diferentes. Objetos de serviço, no entanto, não são, estritamente falando, parte do padrão MVC.

Como você já deve ter percebido, os aplicativos web não precisam necessariamente seguir o padrão MVC. É perfeitamente aceitável que o manipulador execute todo o processamento e simplesmente retorne uma resposta ao cliente. Não é necessário dividir o trabalho em controladores e modelos.

### 1.9.2. Mecanismo de modelo

Um template é um código que pode ser convertido em HTML que é enviado de volta ao cliente em uma mensagem de resposta HTTP. Os templates podem estar parcialmente em HTML ou não estar. Um mecanismo de template gera o HTML final usando templates e dados. Como você deve se lembrar, os mecanismos de template evoluíram de uma tecnologia anterior, SSI.

Existem dois tipos de modelos com diferentes filosofias de design:

- Modelos estáticos ou modelos sem lógica são HTML intercalados com tokens de espaço reservado. Um mecanismo de modelo estático gerará o HTML substituindo esses tokens pelos dados corretos. Há pouca ou nenhuma lógica no próprio modelo. Como você pode ver, isso é semelhante aos conceitos do SSI. Exemplos de mecanismos de modelo estático são CTemplate e Mustache.
- Modelos ativos geralmente contêm HTML também, mas além de tokens de espaço reservado, eles contêm outras construções de linguagem de programação como condicionais, iteradores e variáveis. Exemplos de mecanismos de modelo ativos são Java ServerPages (JSP), Active Server Pages (ASP) e Embedded Ruby (ERB). O PHP começou como um tipo de mecanismo de modelo ativo e evoluiu para sua própria linguagem de programação.

Nós cobrimos muitos dos fundamentos e teorias por trás dos aplicativos web até agora neste capítulo. Se isso parece uma sobrecarga excessiva de minúcias técnicas para você, por favor, aguente firme! Conforme chegamos aos capítulos seguintes, você começará a perceber por que é necessário entender os fundamentos abordados neste capítulo. Enquanto isso, vamos mudar de assunto, prender a respiração e pular nas águas frias da programação em Go — é hora de obter alguma experiência prática. Nas próximas seções, eu o iniciarei no caminho do desenvolvimento de aplicativos web com Go.

## 1.10. Olá, Go

Vamos escrever nosso primeiro aplicativo web Go. Se você não instalou o Go, leia o apêndice A e siga as instruções de instalação. Não se preocupe se você não conhece o pacote net/http que está sendo usado — você aprenderá nos próximos capítulos. Por enquanto, apenas digite o código ( listagem 1.1 ), compile-o e veja como ele funciona. Se você está acostumado a uma linguagem de programação que não diferencia maiúsculas de minúsculas, lembre-se, o código Go diferencia maiúsculas de minúsculas.

Todo o código-fonte deste livro está no GitHub em <https://github.com/sausheong/gwp> .

Listagem 1.1. Um aplicativo web Hello World Go

```go
package main

import (
    "fmt"
    "net/http"
)

func handler(writer http.ResponseWriter, request *http.Request) {
    fmt.Fprintf(writer, "Hello World, %s!", request.URL.Path[1:])
}

func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}
```

Crie um subdiretório no diretório src do seu workspace e nomeie-o first_webapp. Agora vá para esse subdiretório e crie um arquivo chamado server.go. Este será seu arquivo de origem. Então, de um console (ou interface de linha de comando ou prompt de comando), execute este comando:

    $ go install first_webapp

Você pode fazer isso em qualquer diretório. Se seu GOPATH estiver configurado corretamente, isso criará um arquivo executável binário em seu diretório $GOPATH/bin chamado first_webapp. Execute o arquivo executável no console. Como você tem o diretório $GOPATH/bin em seu PATH, você deve conseguir executá-lo de qualquer lugar. Isso iniciará seu aplicativo web Go na porta 8080. É isso!

Agora abra seu navegador e vá para <http://localhost:8080>. A Figura 1.3 mostra o que você deve ver.

Figura 1.3. Primeira captura de tela do aplicativo da web

![alt text](00101.jpg)

Dê uma olhada mais de perto no código. A primeira linha declara que tipo de programa você está escrevendo. A palavra-chave package é seguida pelo nome do pacote. Um programa executável deve sempre estar em um pacote chamado main, e isso é o mesmo para um aplicativo da web. Se você tem alguma experiência com programação de aplicativos da web em outras linguagens (como Ruby, Python ou Java), você pode notar a diferença imediatamente. Nessas linguagens, você geralmente precisa implantar o aplicativo da web em um servidor de aplicativos que fornece um ambiente para seus aplicativos da web serem executados. Em Go, esse ambiente é fornecido pelo pacote net/http e é compilado junto com o resto do seu código para criar um aplicativo da web autônomo prontamente implantável.

A próxima linha importa as bibliotecas necessárias. Você importa bibliotecas Go padrão (pacotes) da mesma forma que importa outras bibliotecas de terceiros. Aqui você está importando dois pacotes: fmt, que permite E/S formatadas (permitindo que você faça coisas como Fprintf ) e http, que é o pacote principal para interagir com HTTP:


```go
    import(
        "fmt"
        "net/http" 
    )
```

Isto é seguido por uma definição de função. Você define uma função chamada handler . O termo handler é frequentemente usado para funções de retorno de chamada acionadas por um evento, e é isso queé usado aqui (embora tecnicamente, pelo menos em Go, isso não seja um manipulador, mas uma função de manipulador — exploraremos isso no capítulo 3 ).

```go
    func handler(writer http.ResponseWriter, request *http.Request) {      
        fmt.Fprintf(writer, "Olá Mundo, %s!", request.URL.Path[1:]) 
    }
```

A função handler tem dois parâmetros de entrada — uma interface ResponseWriter e um ponteiro para uma estrutura Request . Ela pega informações da Request para criar uma resposta HTTP, que é enviada por meio da ResponseWriter . A função Fprintf é chamada com a ResponseWriter , uma string de formato com um único especificador de formato de string ( %s ), seguido pelas informações de caminho extraídas da Request . Como você foi para o endereço <http://localhost:8080>, não há informações de caminho e, portanto, nada é impresso. Se você tivesse ido para o endereço <http://localhost:8080/sausheong/was/here>, a figura 1.4 mostra como ele teria aparecido no navegador.

Figura 1.4. Captura de tela do aplicativo da Web com caminho

![alt text](00107.jpg)

Todo programa que é compilado em um arquivo executável binário deve ter uma função chamada main, onde a execução do programa começa:

```go
func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}
```

A função principal neste programa é direta. Primeiro, você configura o manipulador que você definiu anteriormente para disparar quando a URL raiz (/) for chamada. Então você inicia o servidor para escutar a porta 8080. Para parar o servidor, simplesmente pressione Ctrl-C.

E aí está: um aplicativo web Hello World funcional, escrito em Go!

Começamos com uma explicação de conceitos no início deste capítulo e terminamos em uma corrida de código onde escrevemos um aplicativo web simples (e inútil) em Go. No próximo capítulo, vamos pular para mais código e mostrar como um aplicativo web mais realista (embora ainda não pronto para produção) pode ser escrito com Go e suas bibliotecas padrão. Embora o capítulo 2 ainda possa ser um pouco de corrida de código, você verá como um aplicativo web Go típico pode ser estruturado.

## 1.11. Resumo

- Go é uma linguagem de programação muito adequada para programação web porque permite que aplicativos web escaláveis, modulares, fáceis de manter e de alto desempenho sejam escritos com relativa facilidade.
- Os aplicativos web são programas que retornam HTML ao cliente que faz a chamada por meio de HTTP, portanto, entender bem o HTTP é muito importante ao aprender a escrever aplicativos web.
- HTTP é um protocolo cliente-servidor simples, sem estado e baseado em texto, usado na troca de dados entre um cliente e um servidor.
- Solicitações e respostas HTTP são estruturadas com formatos semelhantes: elas começam com uma linha de solicitação (ou status de resposta), seguida por um ou mais cabeçalhos e um corpo de opção.
- Cada solicitação HTTP tem uma linha de solicitação que contém um método HTTP que indica a ação solicitada ao servidor, sendo os dois mais populares GET e POST.
- Cada resposta HTTP tem uma linha de status de resposta que informa ao cliente que efetua a chamada o status da solicitação.
- Há duas partes principais de qualquer aplicativo web que correspondem a solicitações e respostas: manipuladores e o mecanismo de modelo.
- Os manipuladores recebem solicitações HTTP e as processam.
- O mecanismo de modelo gera HTML que é enviado de volta como parte da resposta HTTP.