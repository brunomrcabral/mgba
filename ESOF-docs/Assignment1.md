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
* Carlos Samouco (up201305187@fe.up.pt)
* Carlos Soares (up201305514@fe.up.pt)
* Diogo Marques (up201305642@fe.up.pt)

###Introdução

![](mgba-256.png)

O mGBA é um emulador da consola portátil Game Boy Advance implementado em C.

Este projeto teve inicio em Abril de 2013 com o objetivo de correr em *hardware* com características inferiores às que outros emuladores suportavam na altura, sem sacrificar a experiência do utilizador nem a portabilidade. Ainda numa versão inicial, os jogos corriam sem grandes problemas pois a implementação original era baseada num outro projeto de emulador da mesma plataforma, mas implementado em *JavaScript*, denominado GBA.js. No entanto são poucos os vestigíos de código encontrados relativamente ao antigo GBA.js devido às várias alterações já realizadas pela equipa do mGBA.

Outros objetivos do autor deste projeto e dos seus colaboradores passa por conseguir um emulador suficientemente rápido capaz de correr em máquinas e dispositivos mais antigos com enorme fiabilidade, de forma a constituir um ambiente para desenvolvimento de *software homebrew* (isto é, *software* não-oficial desenvolvido pela comunidade para esta plataforma), uma boa ferramenta para a realização de *tool-assisted speedruns* (TAS), bem como a construção de um conjunto de recursos inovadores que possam ser reutilizados por outros projetos do mesmo género.

Este projeto integra também um projeto maior, igualmente *open-source*, a biblioteca libretro, que reúne os esforços de vários *developers open-source* na comunidade de *retro-gaming* para a criação de uma plataforma *cross-platform* para correr software e jogos de computador antigos em máquinas mais modernas. Qualquer autor de *software* de emulação é convidado a participar neste projeto.

A versão estável do mGBA à data da elaboração deste relatório era a 0.3.0, com o lançamento da 0.3.1 para breve. É esperada ainda uma nova *milestone* no final deste ano.

###Processo de desenvolvimento

Embora não tenha sido possível identificar um processo de desenvolvimento,

O projeto tem um único proprietário, e um pequeno grupo com cerca de 14 colaboradores até ao momento. No entanto, é possivel que qualquer membro da comunidade GitHub contribua para o projeto. As instruções de contribuição estão bem definidas, apenas será necessário que o utilizador tenha em atenção alguns aspetos e cuidados descritos no documento CONTRIBUTING.md, disponível na raiz do repositório.

O utilizador com a intenção de contribuir deve realizar um *fork* ou um *branch* do repositório na sua versão atual, e após realizar alterações significantes no código, pedir ao proprietário que as incorpore no *branch* principal, através de um *pull request*. No momento do *pull request* será também necessário indicar qual a finalidade daquele código, ou seja, qual o componente que foi implementado ou melhorado, bem como um parágrafo sucinto a explicar essas alterações.

As alterações apenas serão aceites se o código estiver devidamente formatado segundo uma determinada nomenclatura e estilo de código, previamente definida pelo proprietário, se forem pertinentes e se não causarem problemas no funcionamento do programa, estando sujeito portanto a uma análise pelo proprietário.

A melhor forma de avaliar os progressos no código será com base em testes unitários. Estes testes tanto podem ser escritos em código para verificar o correcto funcionamento da unidade de processamento e dos restantes periféricos (dispositivos de entrada e saída, memória, vídeo) ou carregando para a aplicaçaõ um ficheiro contendo uma cópia do software original. No caso dos emuladores, estes ficheiros contendo software designam-se por ROMs, uma vez que são obtidas por processos de dumping da memória ROM contida dentro das cassetes.

Test Driven Development (TDD) é uma técnica de desenvolvimento de software que baseia em um ciclo curto de repetições...

![](commit-graph.PNG)

No momento de escrita deste relatório (3/10/2015), o projeto encontra-se relativamente ativo, com uma média de XX commits por semana, desde a semana com início a 5 de outubro de 2014 até à semana com início a 27 de setembro de 2015, e conta com mais de 2850 commits durante o seu tempo de vida.

![](commit-frequency.PNG)

Além da optimização e organização da estrutura do código base, a equipa está atualmente a fazer *ports* do mGBA para novas plataformas, também elas consolas de jogos (PlayStation Vita, Nintendo 3DS e Nintendo Wii), com base no *feedback* recebido pela comunidade o GitHub e na página oficial do projeto no Bugzilla. Os responsáveis por estes *ports* criaram *branches* no repositório para poder haver algum paralelismo entre o *master* que contém o código base.

###Analise Crítica

#### Commits

O projeto encontra-se ativo, tendo recebido alguns *commits* ao longo do último mês. A frequência dos commits parece-nos normal para um projeto desta dimensão que nasceu de um outro projeto já maduro. 

Acreditamos ainda que este projeto apresenta uma grande margem de evolução, continuando a despertar o interesse de colaboradores, utilizadores e entusiastas do *retro-gaming*. Como grande parte dos *commits* são habitualmente realizados ao fim-de-semana, tudo indica que este projeto seja um pequeno *hobby* do seu proprietário.

Como a base deste emulador está relativamente sólida há algum tempo, tempo este suficiente para garantir a compatibilidade com grande parte dos jogos e *software* comercial lançados para a *Gameboy Advance*, nos últimos meses a equipa tem-se dedicado sobretudo ao *refactoring* do código, procurando melhorias no desempenho geral do programa, à correcção de pequenos *bugs* específicos encontrados durante a execução dos testes de jogabilidade em certos jogos (*playtests*), à implementação de novas funcionalidades na interface gráfica do utilizador, e aos *ports* para outras plataformas.

Os commits são normalmente acompanhados por uma mensagem que quase sempre nos parece pertinente, concisa e perfeitamente explicativa da alteração que foi realizada. Nesta fase do projeto, a maior parte dos commits diz respeito a correções de erros. arece-nos razoável admitir que a grande maioria foi de alguma pertinência e contribuiu para um aumento global da qualidade do projeto.

A realização de *ports* é notável para software que foi inicialmente desenhado para correr num computador com *interface* gráfica e em sistemas operativos como *Windows*, *MacOS* ou *Linux*. 

####Issues

No repositório existe também uma secção de *issues* bastante ativa, com utilizadores e *contributors* a submeter relatórios de *bugs* todas as semanas devidamente acompanhados por uma pequena mensagem a descrever o problema e por vezes uma imagem ou *screenshot* ilustrando a situação descrita. O *feedback* do autor deste projeto é muito responsivo, tendo a maior parte das *issues* resposta ou resolução imediata.

As *issues* são uma excelente forma de definir uma sequência de tarefas a realizar, possíveís melhorias ou correções de *bugs* a fazer que entretanto foram identificados pela comunidade. As *issues* têm uma etiqueta associada (referente à categoria, relevância, urgência dos *bugs* encontrados, etc...) e podem ser adicionadas a uma milestone, ou seja, a um conjunto de outras issues e funcionalidades planeadas que deverão ser resolvidas e/ou implementadas até uma certa data definida pelo proprietário. No momento do presente relatório, 28 das 99 issues publicadas ainda estão em aberto e apenas uma dela foi atribuída a um *developer*. Neste momento, desde o inicio do projeto, foram já concluídas 4 *milestones*, estando ainda duas em aberto para serem concluídas numa data futura. No entanto, uma delas não foi concluída a tempo estando no presente dia quatro dias em atraso com apenas 62% das issues completas, e com a última *issue* dessa *milestone* resolvida há oito dias atrás.

![](milestone-due.PNG)

O volume de testes unitários realizados pelo *top contributor* deste projeto após cada *refactoring* ou correção de *bugs* tem sido relativamente reduzido, levando a eventuais regressões no funcionamento deste *software*. Há um número relativamente elevado de *commits* realizados com o único propósito de corrigir maus comportamentos no código.

###Conclusão



###TODO:
- [x] Descrição do projeto
- [ ] Processo
- [ ] Análise critica
