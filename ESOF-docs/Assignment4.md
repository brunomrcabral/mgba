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
 Cada um destes componentes fornece serviços que são independentes do estado de qualquer um dos outros componentes em cada instante da execução do programa, e portanto é razoável admitir que é possível controlar o seu estado interno em cada momento.
 


### Observabilidade
- Observability: The degree to which it is possible to observe (intermediate and final) test results.

###Isolabilidade
- Isolateability: The degree to which the component under test (CUT) can be tested in isolation.

###Separação de Funcionalidades
- Separation of concerns: The degree to which the component under test has a single, well defined responsibility.

###Inteligibilidade
- Understandability: The degree to which the component under test is documented or self-explaining.

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
