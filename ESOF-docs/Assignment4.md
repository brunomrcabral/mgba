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

##Testabilidade

- **Controllability :** The degree to which it is possible to control the state of the component under test (CUT) as required for testing.
- **Observability :** The degree to which it is possible to observe (intermediate and final) test results.
- **Isolateability :** The degree to which the component under test (CUT) can be tested in isolation.
- **Separation of concerns :** The degree to which the component under test has a single, well defined responsibility**
- **Heterogeneity :** The degree to which the use of diverse technologies requires to use diverse test methods and tools in parallel.

###Controlabilidade
Como já foi referido em relatórios anteriores, o MGBA define um conjunto de elementos que implementam os diferentes controladores de emulação do hardware como por exemplo controladores de som, de vídeo, de inputs e até mesmo de controladores de emulação do CPU.

Cada um destes componentes fornece serviços que são independentes do estado de qualquer um dos outros componentes em cada instante da execução do programa, e portanto é razoável admitir que é possível controlar o seu estado interno em cada momento. Esse estado interno dos diferentes pomponetes do programa pode ser consultado através de um debugger em “mgba/src/debugger/”, que permite assim demonstrar essa modularidade do programa.


### Observabilidade
Não nos foi possível verificar a existência de testes unitários neste repositório, no entanto, existem testes (“mgba/src/platform/test”) que demonstram que esses componentes são controláveis, pois nesta secção é possível definir uma série de parâmetros vareáveis que criam casos de teste. Por exemplo é possível desativar o rendering de vídeo ou controlar o número de fps.  Ainda assim os testes mais relevantes são feitos em módulos que combinam os diferentes componentes. São feitos com recurso a diferentes ROM’s que são postas a correr no programa sendo avaliado se a emulação dessa ROM teve o resultado esperado ou não, pois cada ROM usa diferentes recursos do emulador. No entanto, existem sempre casos de ROM’s que geram novas exceções no programa, o que conduz a erros de execução, que podem acabar por ser reportados por utilizadores do emulador na secção dos issues como já foi referido em entregas anteriores.

###Isolabilidade

###Separação de Funcionalidades
Durante o processo de desenvolvimento de *software* é importante garantir que cada funcionalidade implementada fique confinada, o mais possível, na componente ao qual diz respeito, evitando que o código se torne mais confuso. Nestas condições, código mal estruturado levaria ao aumento do grau de dificuldade na definição e realização de testes unitários. 

Em projetos de grande dimensão deve ser dada particular atenção a este aspeto, de forma a evitar a ocorrência de código mal estruturado, o que dificulta a sua manutenção. A separação de funcionalidades procura resolver os problemas acima referidos: facilita o isolamento da componente a ser testada, aspeto de grande relevância na produção de testes unitários.

###Inteligibilidade
A inteligibilidade do *software* assume também uma enorme relevância no que toca à manutenção, desenvolvimento e teste do *software* em questão. Assim, quanto mais detalhada for a documentação de um programa e melhor organizada for a sua estrutura (como também foi referido nas secções anteriores deste relatório), maior é a facilidade de compreensão do mesmo. Esta facilidade de compreensão que pode ser vista como uma vantagem nas mais variadas situações, como por exemplo na integração de novos colaboradores, no relatório e correcção de *bugs*, na sugestão de novas funcionalidades (levantamento de requisitos).

Em projetos de grandes dimensões como este, a existência de documentação e de uma estrutura de código bem definida possui uma importância acrescida no entendimento do funcionamento de cada componente do *software* a ser desenvolvido. É da responsabilidade do proprietário e dos seus colaboradores promover a consistência e qualidade do código, bem como manter a sua documentação atualizada e acessível a qualquer outro *developer* ou indivíduo que demonstre interesse em participar.

Consideramos que o projeto em estudo perde bastante nestes aspetos agora referidos, pois revela-se pouco detalhado na descrição das classes e das funções nelas existentes, revelando até uma completa ausência de documentação em grande parte dos ficheiros de código fonte, sendo pouco clara quando esta exista, o que torna certos módulos do programa de difícil compreensão. 

###Heterogenidade

- CMake **:** família de ferramentas que tem como objetivo compilar, testar e estruturar *software* que permite realizar configurações independentes de compilador.

- Qt **:** cross-platform application framework that is widely used for developing application software that can be run on various software and hardware platforms com in the underlying codebase, while having the power and speed of native applications;

##Estatísticas de Teste

###Travis-CI

Uma das ferramentas utilizadas pelos colaboradores do projeto na realizaçao testes de integração designa-se por Travis-CI. Esta ferramenta trata-se de um serviço de integração contínuo e distribuído totalmente gratutito e *open source*.

Esta ferramenta permite aos seus utilizadores registarem o seu repositório do GitHub e assim terem os seus testes executados. Sempre que é realizado um *commit* por qualquer colaborador num *branch* do repositório, a ferramente reconhece essa alteração, compilando imediatamente o projeto e correndo todos os testes unitários pré-configurados. O mesmo acontece com os pull requests, onde esta ferramenta é bastante útil, auxiliando o proprietário a aprovar/rejeitar os mesmos.

O Travis-CI suporta diversas linguagens de programação e possui um grau de dificuldade de utilizaçaõ muito acessível. Para configurar será apenas necessário adicionar um novo ficheiro denominado '.travis.yml' na raiz do projeto, bem como outros *scripts* que possam ser necessários executar juntamente com o *script* principal.

No entanto, o proprietário deste projeto não recorre a esta ferramenta para executar tests unitários, servindo-se apenas dela para realizar testes de compilação, como é possível observar. Na raiz do repositório do *mGBA* encontraram-se dois ficheiros relacionados entre si, com nomes ".travis.yml" e ."travis-deps.sh".

###Coverage

In computer science, code coverage is a measure used to describe the degree to which the source code of a program is tested by a particular test suite. A program with high code coverage has been more thoroughly tested and has a lower chance of containing software bugs than a program with low code coverage. Many different metrics can be used to calculate code coverage; some of the most basic are the percent of program subroutines and the percent of program statements called during execution of the test suite.

- Function coverage - Has each function (or subroutine) in the program been called?
- Statement coverage - Has each statement in the program been executed?
- Branch coverage - Has each branch (also called DD-path) of each control structure (such as in if and case statements) been executed? For example, given an if statement, have both the true and false branches been executed? Another way of saying this is, has every edge in the program been executed?
- Condition coverage (or predicate coverage) - Has each Boolean sub-expression evaluated both to true and false?
- 
###Bugzilla

##Análise Crítica
