```
  _____        _         _     __         _        
 |  __ \      | |       | |   /_/        (_)       
 | |__) | ___ | |  __ _ | |_  ___   _ __  _   ___  
 |  _  / / _ \| | / _` || __|/ _ \ | '__|| | / _ \ 
 | | \ \|  __/| || (_| || |_| (_) || |   | || (_) |
 |_|  \_\\___||_| \__,_| \__|\___/ |_|   |_| \___/ 
 ```
##Engenharia de Software - 2015/2016
:floppy_disk:  *Mestrado Integrado em Engenharia Informática e Computação*   :floppy_disk:

Faculdade de Engenharia da Universidade do Porto

###Grupo
* Carlos Jorge Rocha Soares (up201305514@fe.up.pt)
* Carlos Manuel Carvalho Boavista Samouco (up201305187@fe.up.pt)
* Diogo Belarmino Coelho Marques (up201305642@fe.up.pt)

##Introdução

##Graus de Testabilidade

###Controlabilidade
- Controllability: The degree to which it is possible to control the state of the component under test (CUT) as required for testing.

Como já foi referido em relatórios anteriores, o MGBA define um conjunto de elementos que implementam os diferentes controladores de emulação do hardware como por exemplo controladores de som, de vídeo, de inputs e até mesmo de controladores de emulação do CPU.

  Cada um destes componentes fornece serviços que são independentes do estado de qualquer um dos outros componentes em cada instante da execução do programa, e portanto é razoável admitir que é possível controlar o seu estado interno em cada momento. Esse estado interno dos diferentes pomponetes do programa pode ser consultado através de um debugger em “mgba/src/debugger/”, que permite assim demonstrar essa modularidade do programa.


### Observabilidade
- Observability: The degree to which it is possible to observe (intermediate and final) test results.

Não nos foi possível verificar a existência de testes unitários neste repositório, no entanto, existem testes (“mgba/src/platform/test”) que demonstram que esses componentes são controláveis, pois nesta secção é possível definir uma série de parâmetros vareáveis que criam casos de teste. Por exemplo é possível desativar o rendering de vídeo ou controlar o número de fps.  Ainda assim os testes mais relevantes são feitos em módulos que combinam os diferentes componentes. São feitos com recurso a diferentes ROM’s que são postas a correr no programa sendo avaliado se a emulação dessa ROM teve o resultado esperado ou não, pois cada ROM usa diferentes recursos do emulador. No entanto, existem sempre casos de ROM’s que geram novas exceções no programa, o que conduz a erros de execução, que podem acabar por ser reportados por utilizadores do emulador na secção dos issues como já foi referido em entregas anteriores.

###Isolabilidade
- Isolateability: The degree to which the component under test (CUT) can be tested in isolation.

###Separação de Funcionalidades
- Separation of concerns: The degree to which the component under test has a single, well defined responsibility.

###Inteligibilidade
A inteligibilidade do *software* assume uma enorme relevância no que toca à manutenção, desenvolvimento e teste do *software* em questão. Assim, quanto mais detalhada for a documentação de um programa e melhor organizada for a sua estrutura, maior é a facilidade de compreensão do mesmo. Esta facilidade de compreensão que pode ser vista como uma vantagem em diversas situações, como por exemplo na integração de novos colaboradores, na sugestão de novas funcionalidades ou até na correcção de *bugs*.

Em projetos como este, de dimensão considerável, a existência de documentação e de uma estrutura de código bem definida possui uma importância acrescida. É da responsabilidade do proprietário e dos colaboradores promover a consistência e qualidade do código, bem como manter a sua documentação atualizada e acessível a qualquer *developer* ou indivíduo que demonstre interesse em participar no projeto.

Consideramos que o projeto em estudo perde bastante nestes aspetos agora referidos, pois revela-se pouco detalhado na descrição das classes e das funções nelas existentes, revelando até uma completa ausência de documentação em grande parte dos ficheiros de código fonte, ou pouco clara quando esta exista, o que torna certos módulos do programa de difícil compreensão. 


###Heterogenidade
- Heterogeneity: The degree to which the use of diverse technologies requires to use diverse test methods and tools in parallel.

##Estatísticas de Teste

###Travis-CI

Uma das ferramentas usadas para realizar testes de integração neste projeto é o Travis-CI que trata-se de um serviço de integração contínuo e distribuido totalmente gratutito e open-source.
Esta ferramenta permite aos seus utilizadores registarem o seu repositório do GitHub e assim terem os seus testes executados. Sempre que é feito um commit a ferramente reconhece e de imediato compila o projeto e corre todos os testes.
O mesmo acontece com os pull requests.
O Travis-CI suporta diversas linguagens e para ser configurado é apenas necessário adicionar um novo ficheiro denominado '.travis.yml' no diretório raiz do projeto.

CMake é uma família de ferramentas que tem como objetivo compilar, testar e organizar software. Para isso é usado um plataforma simples e configurações de um compilador independente.

Qt é um software desenhado para desenhado para desenvolver outros aplicativos de software.

###Coverage

###Bugzilla
