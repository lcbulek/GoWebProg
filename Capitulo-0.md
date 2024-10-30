# Go para a programação da Web

Sau Sheong Chang

![alt text](00158.jpg)

## Direitos autorais

Para informações on-line e pedidos deste e de outros livros de Manning, visite <www.manning.com> . A editora oferece descontos neste livro quando pedidos em quantidade. Para mais informações, entre em contato

    Departamento de Vendas Especiais        
    Manning Publications Co.        
    20 Baldwin Road        
    PO Box 761        
    Shelter Island, NY 11964        
    E-mail:  orders@manning.com

©2016 por Manning Publications Co. Todos os direitos reservados.

Nenhuma parte desta publicação pode ser reproduzida, armazenada em um sistema de recuperação ou transmitida, de qualquer forma ou por meio eletrônico, mecânico, fotocópia ou outro, sem a permissão prévia por escrito do editor.

Muitas das designações usadas por fabricantes e vendedores para distinguir seus produtos são reivindicadas como marcas registradas. Onde essas designações aparecem no livro, e a Manning Publications estava ciente de uma reivindicação de marca registrada, as designações foram impressas em letras maiúsculas iniciais ou todas em maiúsculas.

![alt text](00127.jpg) Reconhecendo a importância de preservar o que foi escrito, é política da Manning ter os livros que publicamos impressos em papel sem ácido, e nós exercemos nossos melhores esforços para esse fim. Reconhecendo também nossa responsabilidade de conservar os recursos do nosso planeta, os livros da Manning são impressos em papel que é pelo menos 15 por cento reciclado e processado sem cloro elementar.

![alt text](00089.jpg)

    Manning Publications Co.
    20 Baldwin Road
    Caixa Postal 761
    Shelter Island, NY 11964

Editor de desenvolvimento: Marina Michaels
Editores de desenvolvimento técnico: Glenn Burnside Michael Williams
Editor de revisão: Ozren Harlovic
Editor de projeto: Kevin Sullivan
Editor de texto: Liz Welch
Revisor: Elizabeth Martin
Revisor técnico: Jimmy Frasché
Compositor: Marija Tudor
Designer de capa: Marija Tudor

ISBN: 9781617292569

Impresso nos Estados Unidos da América

1 2 3 4 5 6 7 8 9 10 – MBE – 21 20 19 18 17 16

## Prefácio

Os aplicativos da Web existem de uma forma ou de outra desde o início da World Wide Web em meados da década de 1990. Eles começaram entregando apenas páginas da Web estáticas, mas logo escalaram e evoluíram para uma variedade estonteante de sistemas dinâmicos entregando dados e funções. Minha própria jornada no desenvolvimento de aplicativos para a Web começou na mesma época, em meados da década de 1990, e acabei passando a maior parte da minha carreira profissional projetando, desenvolvendo e gerenciando equipes no desenvolvimento de aplicativos da Web em larga escala. No mesmo período, escrevi aplicativos da Web em várias linguagens de programação e usando várias estruturas, incluindo Java, Ruby, Node.js, PHP, Perl, Elixir e até Smalltalk.

Eu tropecei no Go alguns anos atrás, e o que funcionou muito bem para mim foi a simplicidade e a franqueza refrescante da linguagem. Fiquei ainda mais impressionado quando percebi que eu poderia escrever rapidamente aplicativos da web completos (e serviços) que são rápidos e escaláveis ​​apenas com as bibliotecas padrão do Go. O código é direto, fácil de entender e pode ser compilado de forma rápida e fácil em um único arquivo binário implementável. Eu não preciso mais adicionar servidores de aplicativos para escalar ou para tornar meu aplicativo da web capaz de produção. Nem preciso dizer que todos esses elementos fizeram do Go minha nova linguagem favorita para escrever aplicativos da web.

A escrita de aplicativos da web mudou drasticamente ao longo dos anos, de conteúdo estático para dados dinâmicos sobre HTTP, de conteúdo HTML entregue do servidor para aplicativos de página única do lado do cliente consumindo dados JSON sobre HTTP. Quase assim que os primeiros aplicativos da web foram escritos, frameworks de aplicativos da web apareceram, tornando mais fácil para os programadores escrevê-los. Vinte anos depois, a maioria das linguagens de programação tem pelo menos um framework de aplicativo da web — e muitas têm dezenas — e a maioria dos aplicativos escritos hoje são aplicativos da web.

Embora as populares estruturas de aplicativos da web tenham facilitado a escrita de aplicativos da web, elas também ocultaram muito do encanamento subjacente. Tornou-se cada vez mais comum encontrar programadores que nem mesmo entendem como a World Wide Web funciona escrevendo aplicativos da web. Com o Go, encontrei uma ótima ferramenta para ensinar os fundamentos da programação de aplicativos da web, corretamente. Escrever aplicativos da web é direto e simples novamente. Tudo está lá — sem bibliotecas e dependências externas. É tudo sobre HTTP novamente e como entregar conteúdo e dados por meio dele.

Então, com isso em mente, abordei Manning com uma ideia para um livro sobre linguagem de programação Go que se concentra em ensinar alguém a escrever aplicativos da web do zero, usando nada além das bibliotecas padrão. Manning rapidamente apoiou minha ideia e deu sinal verde para o projeto. O livro demorou um pouco para ficar pronto, mas o feedback do programa de acesso antecipado (MEAP) foi encorajador. Espero que você ganhe muito e goste de ler este livro tanto quanto eu gostei de escrevê-lo.

## Agradecimentos

Este livro começou com uma ideia de ensinar os conceitos básicos de programação web com Go, usando nada mais do que as bibliotecas padrão. Eu não tinha certeza se isso funcionaria, mas os leitores que pagaram dinheiro arduamente ganho para comprar meu MEAP ao longo do caminho me deram encorajamento e motivação para levar a ideia adiante. Aos meus leitores, obrigado!

Escrever livros é um esforço de equipe e, embora meu nome apareça na capa deste, ele só existe por causa dos esforços de um grande número de pessoas:

- Marina Michaels, minha editora trabalhadora e eficiente do outro lado do mundo, trabalhou incansavelmente ao meu lado, sempre pronta para acomodar sua agenda aos nossos fusos horários dramaticamente diferentes.
- A equipe ampliada de Manning: Liz Welch, editora de texto, e Elizabeth Martin, revisora, que com seus olhos de águia ajudaram a detectar meus erros; Candace Gillhoolley e Ana Romac, que me ajudaram a comercializar e promover este livro; e Kevin Sullivan e Janet Vail, que trabalharam para pegar meu manuscrito bruto e transformá-lo em um livro de verdade.
- Jimmy Frasché, que fez uma revisão técnica completa do manuscrito, e meus revisores, que deram feedback valioso em quatro estágios do desenvolvimento do manuscrito: Alex Jacinto, Alexander Schwartz, Benoit Benedetti, Brian Cooksey, Doug Sparling, Ferdinando Santacroce, Gualtiero Testa, Harry Shaun Lippy, James Tyo, Jeff Lim, Lee Brandt, Mike Bright, Quintin Smith, Rebecca Jones, Ryan Pulling, Sam Zaydel e Wes Shaddix
- Meus amigos da comunidade Singapore Go que me ajudaram a divulgar meu novo livro assim que o MEAP foi lançado, especialmente Kai Hendry, que fez um longo vídeo com seus comentários sobre meu livro
Gostaria também de agradecer aos criadores do Go — Robert Griesemer, Rob Pike e Ken Thompson — assim como aos colaboradores do net/http, html/template e outras bibliotecas padrão da web, especialmente Brad Fitzpatrick, sem os quais eu provavelmente não teria nada sobre o que escrever!

Por último, mas certamente não menos importante, gostaria de agradecer à minha família — o amor da minha vida, Wooi Ying, e meu filho mais alto que eu agora, Kai Wen. Espero que, ao escrever este livro, eu seja uma inspiração para ele e que ele logo pegue meu livro com orgulho e aprenda com ele.

## Sobre este livro

Este livro apresenta os conceitos básicos de escrita de um aplicativo web usando a linguagem de programação Go, do zero, usando nada além das bibliotecas padrão. Embora haja seções que discutem outras bibliotecas e outros tópicos, incluindo testes e implantação de aplicativos web, o objetivo principal do livro é ensinar programação web usando apenas bibliotecas padrão Go.

O leitor deve ter habilidades básicas de programação em Go e conhecer a sintaxe Go. Se você não conhece programação em Go, eu o aconselharia a conferir Go in Action de William Kennedy com Brian Ketelsen e Erik St. Martin, também publicado pela [Manning](www.manning.com/books/go-in-action). Outro bom livro para ler é The Go Programming Language (Addison-Wesley 2015), de Alan Donovan e Brian Kernighan. Como alternativa, há muitos tutoriais gratuitos sobre Go, incluindo o A Tour of Go do site Go (tour.golang.org).

## Roteiro

O livro inclui dez capítulos e um apêndice.

O Capítulo 1 apresenta o uso de Go para aplicativos web e discute por que ele é uma boa escolha para escrever aplicativos web. Você também aprenderá sobre os principais conceitos do que são aplicativos web, incluindo uma breve introdução ao HTTP.

O Capítulo 2 mostra como criar um aplicativo web típico com Go, guiando você passo a passo pela criação de um fórum simples na Internet.

O Capítulo 3 aborda os detalhes do tratamento de solicitações HTTP usando o pacote net/http . Você aprenderá como escrever um servidor web Go para ouvir solicitações HTTP e como incorporar manipuladores e funções de manipulador que processam essas solicitações.

O Capítulo 4 continua com os detalhes do tratamento de solicitações HTTP — especificamente, como Go permite que você processe as solicitações e responda adequadamente. Você também aprenderá como obter dados de formulários HTML e como usar cookies.

O Capítulo 5 se aprofunda no mecanismo de template Go fornecido nos pacotes text/template e html/template . Você aprenderá sobre os vários mecanismos fornecidos pelo Go e sobre o uso de layouts no Go.

O Capítulo 6 discute estratégias de armazenamento usando Go. Você aprenderá sobre armazenamento de dados na memória usando structs, no sistema de arquivos usando CSV e o formato binário gob, bem como usar SQL e mapeadores SQL para acessar bancos de dados relacionais.

O Capítulo 7 mostra como criar serviços web usando Go. Você aprenderá como criar e analisar XML e JSON com Go, e como um serviço web simples pode ser escrito usando Go.

O Capítulo 8 fornece insights sobre as maneiras pelas quais você pode testar seu aplicativo web Go em vários níveis, incluindo testes unitários, testes de benchmark e testes HTTP. Este capítulo também discute brevemente bibliotecas de testes de terceiros.

O Capítulo 9 fala sobre como você pode alavancar a simultaneidade Go em seu aplicativo web. Você aprenderá sobre simultaneidade Go e como pode melhorar o desempenho de um aplicativo web fotomosaico usando simultaneidade Go.

O Capítulo 10 encerra o livro mostrando como você pode implementar seu aplicativo web. Você aprenderá como implementar em servidores autônomos e na nuvem (Heroku e Google App Engine), bem como em contêineres Docker.

O apêndice fornece instruções para instalar e configurar o Go em diferentes plataformas.

## Convenções de código e downloads

Este livro contém muitos exemplos de código-fonte, tanto em listagens numeradas quanto em linha com texto normal. Em ambos os casos, o código-fonte é formatado em uma fonte de largura fixa como esta para separá-lo do texto comum. Às vezes, o código está em negrito para destacar o código que foi alterado em relação às etapas anteriores do capítulo ou o código que é discutido no texto ao redor.

Além disso, cores são usadas para destacar comandos de código e saída de código:

```bash
curl -i 127.0.0.1:8080/write
HTTP/1.1 200 OK
Date: Tue, 13 Jan 2015 16:16:13 GMT
Content-Length: 95
Content-Type: text/html; charset=utf-8
```

```html
<html>
    <head>
        <title>Go Web Programming</title>
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
</html>
```

Os leitores de livros impressos que desejam ver esse código de cores destacado (e todas as figuras coloridas) podem acessar [www.manning.com/books/go-web-programming](www.manning.com/books/go-web-programming) para se registrar e obter seu e-book gratuito nos formatos PDF, ePub e Kindle.

Exemplos de código usados ​​ao longo do livro também estão disponíveis em [www.manning.com/books/go-web-programming](www.manning.com/books/go-web-programming) e em [github.com/sausheong/gwp](github.com/sausheong/gwp).

## Sobre o autor

![alt text](00117.jpg)

SAU SHEONG CHANG é agora o Diretor Executivo de Tecnologia Digital na Singapore Power. Antes disso, ele foi Diretor de Engenharia de Consumo na PayPal. Ele é ativo nas comunidades de desenvolvedores Ruby e Go, e escreveu livros, contribuiu para projetos de código aberto e falou em meetups e conferências.

## Autor Online

A compra do Go Web Programming inclui acesso gratuito a um fórum privado da web administrado pela Manning Publications; você pode fazer comentários sobre o livro, fazer perguntas técnicas e receber ajuda do autor e de outros usuários. Para acessar o fórum e se inscrever nele, aponte seu navegador para <www.manning.com/books/go-web-programming> . Esta página fornece informações sobre como entrar no fórum após se registrar, que tipo de ajuda está disponível e as regras de conduta no fórum.

O compromisso de Manning com nossos leitores é fornecer um local onde um diálogo significativo entre leitores individuais e entre leitores e o autor possa ocorrer. Não é um compromisso com nenhuma quantidade específica de participação por parte do autor, cuja contribuição para o fórum permanece voluntária (e não remunerada). Sugerimos que você tente fazer algumas perguntas desafiadoras ao autor para que seu interesse não se desvie!

O fórum do autor online e os arquivos de discussões anteriores estarão acessíveis no site da editora enquanto o livro estiver em circulação.

## Sobre a ilustração da capa

A figura na capa de Go Web Programming tem a legenda “Homem em traje medieval”. A ilustração de Paolo Mercuri (1804–1884) foi retirada de “Costumes Historiques”, um compêndio multivolume de trajes históricos dos séculos XII, XIII, XIV e XV, reunido e editado por Camille Bonnard e publicado em Paris nas décadas de 1850 ou 1860. O século XIX viu um interesse crescente em locais exóticos e em tempos passados, e as pessoas eram atraídas por coleções como esta para explorar o mundo em que viviam — bem como o mundo do passado distante.

A variedade colorida das ilustrações de Mercuri nesta coleção histórica nos lembra vividamente de quão culturalmente distantes as cidades e regiões do mundo eram algumas centenas de anos atrás. Nas ruas ou no campo, as pessoas eram fáceis de localizar — às vezes com um erro de não mais de uma dúzia de milhas — apenas por suas roupas. Sua posição na vida, bem como seu comércio ou profissão, podiam ser facilmente identificados. Os códigos de vestimenta mudaram ao longo dos séculos, e a diversidade por região, tão rica em um momento, desapareceu. Hoje, é difícil distinguir os habitantes de um continente de outro, muito menos as cidades ou países de onde vêm, ou seu status social ou profissão. Talvez tenhamos trocado a diversidade cultural por uma vida pessoal mais variada — certamente uma vida tecnológica mais variada e de ritmo mais rápido.

Em uma época em que é difícil distinguir um livro de informática do outro, Manning celebra a inventividade e a iniciativa do setor de informática com capas de livros baseadas na rica diversidade da vida regional de muitos séculos atrás, trazida de volta à vida pelas imagens de Mercuri.
