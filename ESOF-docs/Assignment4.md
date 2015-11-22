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
Como já foi referido em relatórios anteriores, o **mGBA** implementa uma máquina virtual constutída por vários elementos que controlam os diferentes controladores de emulação do hardware como por exemplo controladores de som, de vídeo, de inputs e até mesmo de controladores de emulação do CPU.

Cada um destes componentes fornece serviços que são independentes do estado de qualquer um dos outros componentes em cada instante da execução do programa, e portanto é razoável admitir que é possível controlar o seu estado interno em cada momento. Esse estado interno dos diferentes pomponetes do programa pode ser consultado através de um debugger em “mgba/src/debugger/”, que permite assim demonstrar essa modularidade do programa.

### Observabilidade
Não foi possível verificar a existência de testes unitários escritos em código neste repositório. Foram encontrados no entanto testes de outras naturezas no diretório ```/src/platform/test``` que demonstram em que medida esses componentes são controláveis, sendo possível definir uma série de parâmetros variáveis que criam casos de teste. 

Visto que se trata de um **emulador**, seria correto afirmar que a própria utilização deste programa define um caso de teste. Com efeito, é possível realizar **testes de integração** com recurso a diferentes ficheiros ROM que são colocados a correr na **máquina virtual**, sendo posteriormente avaliado se a emulação dessa ROM teve o resultado esperado ou não. Isto acontece porque o *software* contido em cada ROM foi programado para utilizar de forma distinta os vários **recursos** da máquina virtual bem como do dispositivo a ser emulado.

Foi ainda disponibilizado pelo autor no *site* oficial do projeto uma *suite* de testes bastante completa que avalia uma série de operações executadas com maior frequência na máquina virtual:

> In the interest of furthering the state of Game Boy Advance emulation, I've been writing a test suite that tests various aspects of hardware. At the moment, it only tests timing operations, but way more will be coming in the future. 

> -- endrift, https://forums.mgba.io/showthread.php?tid=18

Embora seja referido na página que este ficheiro ROM realiza apenas testes de *timing* ao sistema, a versão disponibilizada à data de elaboração deste relatório contava ainda com testes de acesso à memória e testes de acesso aos registos de *hardware* da máquina virtual. É possível afirmar que a informação que consta nesse tópico encontra-se desatualizada, pois na realidade o programa atual encontra-se muito mais completo.

![](Assignment4/test-select.PNG)

São frequentes os casos de ROMs nunca antes testadas gerarem exceções no programa ao pedirem certas funcionalidades da máquina virtual que se encontram incompletas ou que ainda não foram implementadas em código, o que conduz a erros de execução e a comportamentos menos previsíveis por parte do programa. Estas sintomas são normalmente sinónimo de uma má cobertura de código, isto é, condições ou variáveis existentes no em código que raramente são testadas. Embora os utilizadores desconheçam o funcionamento interno da máquina virtual, grande parte destas situações acabam por ser publicadas por estes na secção de *issues* do repositório como já foi referido nas entregas anteriores. Os últimos progressos no desenvolvimento deste *software* têm sido conseguidos sobretudo graças a estes testes de jogabilidade realizados pelos utilizadores.

###Isolabilidade
A maior parte das classes dos diferentes pacotes faz uso de outras classes e métodos pertencentes a outros pacotes, estando estas intimamente ligadas e interdependentes. Numa situação destas seria correto afirmar que ao testarmos um componente de um determinado módulo estamos também a testar, indiretamente, outros componentes de diferentes módulos.

A única isolabilidade que merece aqui destaque está na separação das funcionalidades dependentes e não dependentes do sistema operativo, o que permite a realização de *ports* para outras plataformas.

###Separação de Funcionalidades

Durante o processo de desenvolvimento de *software* é importante garantir que cada funcionalidade implementada fique confinada, o mais possível, na componente ao qual diz respeito, evitando que o código se torne mais confuso. Um fragmento de *software* com código mal estruturado conduziria ao aumento do grau de dificuldade na definição e realização de testes unitários. 

Em projetos de grande dimensão deve ser dada uma atenção especiala estes aspetos, de forma a evitar a ocorrência de código mal estruturado que aumentaria o custo da sua manutenção. A separação de funcionalidades procura resolver os problemas acima referidos: facilita o isolamento da componente a ser testada, aspeto de grande relevância na produção de testes unitários.

O mGBA apresenta-se dividido em seis packages:

- gba **:** responsável pela implementação de uma máquina virtual na máquina hospedeira que serve como base para a simulação do comportamento do hardware original da consola Game Boy Advance. 
- arm **:** implementa um sistema de recompilação dinâmica das instruções de microprocessadores da família ARM7, utilizado como unidade de processamento central da Game Boy Advance.
- platform  **:** implementa diversas interfaces para frameworks e APIs (application programming interfaces) de terceiros específicas para cada sistema operativo a correr nas diferentes plataformas
-  third-party **:** contém bibliotecas open source de terceiros (third-party libraries) independentes da plataforma alvo que acrescentam novas funcionalidades ao sistema com o mínimo de alterações no código base

###Inteligibilidade
A inteligibilidade do *software* assume também uma enorme relevância no que toca à manutenção, desenvolvimento e teste do *software* em questão. Assim, quanto mais detalhada for a documentação de um programa e melhor organizada for a sua estrutura (como também foi referido nas secções anteriores deste relatório), maior é a facilidade de compreensão do mesmo. Esta facilidade de compreensão que pode ser vista como uma vantagem nas mais variadas situações, como por exemplo na integração de novos colaboradores, no relatório e correcção de *bugs*, na sugestão de novas funcionalidades (levantamento de requisitos).

Em projetos de grandes dimensões como este, a existência de documentação e de uma estrutura de código bem definida possui uma importância acrescida no entendimento do funcionamento de cada componente do *software* a ser desenvolvido. É da responsabilidade do proprietário e dos seus colaboradores promover a consistência e qualidade do código, bem como manter a sua documentação atualizada e acessível a qualquer outro *developer* ou indivíduo que demonstre interesse em participar.

Consideramos que o projeto em estudo perde bastante nestes aspetos agora referidos, pois revela-se pouco detalhado na descrição das classes e das funções nelas existentes, revelando até uma completa ausência de documentação em grande parte dos ficheiros de código fonte, sendo pouco clara quando esta exista, o que torna certos módulos do programa de difícil compreensão. 

###Heterogenidade

- CMake **:** família de ferramentas que tem como objetivo compilar, testar e estruturar *software* que permite realizar configurações independentes de compilador.

- Qt **:** cross-platform application framework that is widely used for developing application software that can be run on various software and hardware platforms com in the underlying codebase, while having the power and speed of native applications;

##Estatísticas de Teste

###Travis-CI

Uma das ferramentas utilizadas pelos colaboradores do projeto na realizaçao testes de integração designa-se por Travis-CI. Esta ferramenta trata-se de um serviço de integração contínuo e distribuído totalmente gratutito e *open source*. O **Travis-CI** permite aos seus utilizadores registarem na base de dados o seu repositório do GitHub e assim terem os seus **testes** executados. Sempre que é realizado um *commit* por qualquer colaborador num *branch* do repositório, esta ferramenta reconhece essa alteração, compilando imediatamente o projeto e correndo todos os testes unitários pré-configurados. O mesmo acontece com os *pull requests*, onde esta ferramenta é igualmente bastante útil, visto que auxilia os colaboradores na aprovação dos mesmos. (EXPLICAR APROVAÇÂO)

O Travis-CI suporta diversas linguagens de programação e possui um grau de dificuldade de utilização relativamente acessível. Para configurar será apenas necessário adicionar um novo ficheiro denominado '.travis.yml' na raiz do repositório, bem como um conjunto de *scripts* no formato *Bash* que eventualmente sejam necessários para executar em paralelo com o *script* de compilação principal.

Apesar das vantagens que foram referidas nos parágrafos anteriores, o proprietário deste projeto não tira partido máximo das funcionalidades do **Travis-CI**, pois não recorre a esta ferramenta para executar testes unitários, servindo-se apenas dela para realizar **testes de compilação**, como é possível observar após uma análise cuidadosa do repositóriodo **mGBA**. Na raiz do repositório encontraram-se ainda dois ficheiros relacionados com esta ferrametna, com nomes ".travis.yml" e ."travis-deps.sh".

###Coverage

In computer science, code coverage is a measure used to describe the degree to which the source code of a program is tested by a particular test suite. A program with high code coverage has been more thoroughly tested and has a lower chance of containing software bugs than a program with low code coverage. Many different metrics can be used to calculate code coverage; some of the most basic are the percent of program subroutines and the percent of program statements called during execution of the test suite.

- Function coverage - Has each function (or subroutine) in the program been called?
- Statement coverage - Has each statement in the program been executed?
- Branch coverage - Has each branch (also called DD-path) of each control structure (such as in if and case statements) been executed? For example, given an if statement, have both the true and false branches been executed? Another way of saying this is, has every edge in the program been executed?
- Condition coverage (or predicate coverage) - Has each Boolean sub-expression evaluated both to true and false?

###Gameboy Advance Test Suite 

Para uma posterior análise de cobertura de testes,  transferimos a [última versão](http://www.emucr.com/2015/11/mgba-git-20151122.html) compilada disponível na Internet, bem como a *suite* de testes referida nas secções anteriores, disponibilizada pelo autor. Em seguida, carregámos esse ficheiro ROM ```suite.gba``` no mGBA e executámos todos os testes disponíveis no momento (três), sendo que obtvemos os seguintes resultados:

![](Assignment4/test-all.png)

A versão testada do programa conseguiu passar todos os testes de memória (1552 dos 1552 testes unitários realizados), não tendo no entanto conseguido obter pontuação máxima nos testes de *timing* (92.4%, 1164 dos 1260 casos testados com sucesso) nem nos testes de acesso aos registos de *hardware* (93.4%, 114 dos 122 casos testados com sucesso), resultados bastante satisfatórios quando comparados com os resultados obtidos por outros emuladores de **Game Boy Advance**, como se pode constatar na seguinte lista:

**Memory Tests**
- mGBA (master): 1552 passes
- NO$GBA 2.8b: 1394 passes
- VBA-M 2.0.0 beta 2: 1375 passes

**I/O Read Tests**
- mGBA: 114 passes
- NO$GBA 2.8b: 99 passes
- VBA-M 2.0.0 beta 2: 99 passes

**Timing Tests**
- mGBA: 1164 passes
- NO$GBA 2.8b: 759 passes
- VBA-M 2.0.0 beta 2: 680 passes
- 
Apesar do mGBA ter apresentado excelentes resultasdos face a programas equivalentes, existem funcionalidades que não são possiveis de testar, como por exemplo a sua interface gráfica. O que poderá, de certa forma, atenuar um pouco a sua falta de cobertura.

##Análise Crítica
