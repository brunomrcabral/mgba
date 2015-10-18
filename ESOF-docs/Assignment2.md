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

###Levantamento de Requisitos

Apesar de ter sido marioritariamente desenvolvido pelo seu proprietário, o mGBA depende também dos seus *main contributors* que submetem *pull requests* com as suas ideias e dos seus *stakeholders*, isto é, das pessoas que têm influência na elaboração dos requisitos. No contexto deste projeto, os *stakeholders* representam um público alvo mais específico, com conhecimentos básicos nesta área, a comunidade de *retro gaming*, pois são sobretudo estes que contribuem para a melhoria da qualidade global do *software*.

No contexto dos emuladores como o mGBA, ter qualidade significa ser capaz de garantir a compatibilidade com a maior parte do *software* e dos periférios lançados para o dispositivo a ser emulado. São os stakeholders que vão dando conta de eventuais *bugs* na aplicação, que se mostram exigentes e insatisfeitos pelas imperfeições no resultado obtido e propõem novas funcionalidades para complementarem a sua experiência de utilização deste *software*.

Existem dois tipos de requisitos em engenharia de *software* também associados a este projeto:

- requisitos funcionais (ou capacidades) descrevem as funcionalidades que se espera que o sistema disponibilize, de uma forma completa e consistente (expetativas do utilizador, atentendo aos propósitos para o qual o sistema foi desenvolvido) **:** funcionalidades da *interface* gráfica de utilizador, suporte a leitura de diversos formatos de ficheiros e a funcionalidades não conseguidas na máquina real sem recorrer à emulação

- requisitos não-funcionais referem-se a aspetos não-funcionais do sistema, como restrições nas quais o sistema deve operar ou propriedades emergentes do sistema (utilidade, desempenho, suporte, escalabilidade) **:** possibilidade do produto final suportar mais do que um dispositivo ou plataforma, ...

####Motivação

A motivação deste projeto assenta de igual forma em requisitos funcionais e não funcionais que foram previamente definidos no 
O principal propósito do projeto seria a criação de um novo emulador capaz de correr grande parte dos jogos e *software* desenvolvidos para a consola *Game Boy Advance* em máquinas e dispositivos com requisitos inferiores aos de outros emuladores existentes na atualidade. 

O próprio autor definiu alguns destes objetivos e requisitos aquando o início do desenvolvimento deste projeto, após uma análise por comparação com outros emuladores *open-source* e comerciais disponíveis na *Internet*, tendo a comunidade contribuido com os restantes e mais variados requisitos ao longo dos últimos meses. Estas novas funcionalidades sugeridas são as que estão habitualmente presentes em *software* do mesmo género, conferindo características que distingue este de *software* equivalente. Entre os requisitos enunciados pelo autor no documento README. presente na raiz deste repositório, destacam-se os seguintes, todos eles conseguidos até ao momento de elaboração deste relatório:

###Casos de Utilização

- compatibilidade com grande parte dos periféricos e jogos da Game Boy Advance
- emulação rápida, capaz de executar em tempo real mesmo em computadores e dispositivos com características inferiores
- ports para outras plataformas recorrendo a *frameworks* como Qt/SDL
- *frameskipping* configurável
- suporte a *screenshots* (capturas de ecrã) e *cheat codes*
- suporte a *savestates* e visualização dos mesmos na *interface* gráfica do utilizador
- gravação de vídeos
- possibilidade de mapear os botões em qualquer dispositivo de entrada ligado ao computador
- suporte a leitura de ficheiros nos formatos ZIP e 7Zip
- suporte a *patches* IPS, UPS e BPS
- suporte a debugging recorrendo a uma *interface* em linha de comandos
- suporte a *multiplayer* em rede utilizando um link cable emulado
- suporte à linguagem de *scripting* Lua
- ferramentas de *debugging* mais completas

O mGBA trata-se de um emulador de Game Boy Advance, ou seja, é neste caso, um software que permite ao computador ter o comportamento de um Game Boy Advance podendo assim correr ROMs (onde está a cópia do jogo). Na última versão do emulador, também já é possível correr software homebrew de 3 novas plataformas, sendo estas Nintendo 3DS, Nintendo Wii, e PlayStation Vita.

###Análise de Requisitos

- classificação: agrupamento de requisitos em "módulos" para facilitar a visão global do funcionamento pretendido para o sistema;
- resolução de conflitos: dada a multiplicidade e diversidade de papéis das partes interessadas envolvidas na captura e análise de requisitos, é inevitável a existência de conflitos nos requisitos identificados; é importante resolver estes conflitos o mais breve possível;
- priorização: consiste na atribuição de uma "prioridade" a cada requisito (por exemplo elevada/média/baixa); obviamente, este pode ser um fator gerador de conflitos;
- confirmação: é confirmada com as partes interessadas a completude dos requisitos, sua consistência e validade (de acordo com o que se pretende do sistema).
- 

A principal fonte de requisitos correntes provém dos *bug reports*/*issues* e dos *pull requests* existentes no repositório do GitHub. Ambos são frequentados tanto pela *core team* (o proprietário deste projeto e os seus *main contributors*

Muitos dos requisitos já foram classificados como completos restando apenas alguns requisitos não funcionais que são progressivamente criados com base na parte do projeto já realizada. Dos requisitos inicialmente definidos restam apenas serem focados alguns requisitos não funcionais passando por melhorias na performance, eficiencia ou mesmo portabilidade.

Nem todos os problemas levantados pela comunidade merecem a mesma atenção a nível de tempo e recursos. Para que uma ideia seja posta em prática é necessário que pelo menos um dos desenvolvedores aceite implementá-la, ou que a própria pessoa que teve a ideia tenha a iniciativa de a implementar, fazendo depois um pull request.

####Bugs/Issues

No repositório existe também uma secção de *issues* bastante ativa, com vários utilizadores e *contributors* a fazer levantamentos de *bugs* com alguma frequência ou a sugerir novas funcionalidades, todos eles devidamente acompanhados por uma pequena mensagem a relatar o problema e muitas vezes por uma imagem ou captura de ecrã ilustrando a situação descrita. 

Após terem sido detetados esses bugs, o responsável pela gestão do projeto, com recurso ao [Bugzilla](https://endrift.com/mgba/bugs/describecomponents.cgi) (*Bug-Tracking System*), detalha e cataloga os *bugs* de acordo com o tipo de layer do software onde estão a ocorrer, permitindo uma boa organização dos problemas de cada componente do programa. Além disso, a cada bug é atribuida uma prioridade de resolução bem como a versão da *milestone* na qual será resolvido.

####Pull Requests

O utilizador com a intenção de contribuir com novas funcionalidades para este projeto deverá fazer um *fork* ou um *branch* do repositório na sua versão atual e pedir ao proprietário que as incorpore no *branch* principal (ou *master*) através de um *pull request*, após ter realizado alterações significativas no código. No momento do *pull request* será também necessário indicar a finalidade daquele código, ou seja, qual a componente que foi implementada ou alterada bem como um parágrafo onde explique sucintamente esssas alterações e a sua motivação.

###Especificação de Requisitos

Dado que não foi encontrado nenhum documento com a descrição dos requisitos funcionais e não funcionais do software em questão (também conhecido por *software requirements specification* ou SRS) assume-me que este não foi criado devendo-se possivelmente à pequena dimensão do projeto.

Este tipo de documento que estabelece os termos de condição entre os clientes e os desenvolvedores em relação ao que o produto final deve ou não corresponder, apesar de ser bastante importante não faria grande sentido neste tipo de projeto pois está a ser desenvolvido por colaboradores voluntários sem elevado grau de compromisso.

Neste caso, cabe ao único autor do projeto decidir o rumo que este deve tomar ao longo do seu ciclo de desenvolvimento, quais as alterações a fazer com base em *milestones* criadas pelo mesmo e tentar sempre que possível cumprir os prazos e datas limites estipuladas pelo próprio.

###Validação de Requisitos

A validação de requisitos consiste em demostrar que os requisitos levantados no processo de negociação com o cliente definem o sistema que este realmente deseja. Trata-se assim do processo onde se avalia a consistência dos pedidos que o cliente faz e se valida esses pedidos como forma de evitar erros de requisitos e diminuir os custos de desenvolvimento.

Numa fase inicial, os *pull requests* e as alterações submetidas pelos utilizadores estão sujeitas a um processo de validação automático antes de serem aprovadas. Após termos analisado da estrutura do repositório, verificou-se que este foi configurado para utilizar a ferramenta Travis-CI, utilizada pelo *GitHub* na realização automaticamente testes de compilação sobre o *source code* submetido nos *pull requests*, rejeitando código que não passe nos mesmos.

Existe ainda um processo de análise e validação manual feita pelo proprietário deste projeto. As alterações submetidas pelos utilizadores devem ser pertinentes e não devem provocar alterações significantes no comportamento do código nem regressões nos testes de compatibilidade do *software*.

O GitHub disponibiliza ainda métodos de etiquetação dos *issues*, de forma a possibilitar a sua classificação em diferentes categorias e prioridades, contribuindo para uma maior organização das tarefas a desenvolver. Consultando a lista de *issues* dos últimos cinco meses, é possível classificá-los em três categorias diferentes: *bugs*, *minor bugs* e *enhancements*. Todos os *issues* que sejam considerados novas funcionalidades e que não corrijam ou melhorem componentes do emulador já implementados em código são habitualmemente classificados como "enhancements" (melhorias), recebendo a menor das prioridades. Os *minor bugs* são *bugs* efetivamente presentes na versão atual do *software* mas que se manifestam em poucos casos, sendo pouco frequentes ou difíceis de reproduzir num cenário típico de utilização, recebendo portanto prioridade normal. Finalmente, existem os *issues* classificados como *bugs* pelo autor deste projeto, que retratam casos mais severos dos *minor bugs* anteriormente referidos, podendo estar associados a *crashes* ou a comportamentos bastante erráticos do *software*, sendo que estes recebem a atenção máxima por parte da equipa de desenvolvimento. Apesar de a maioria dos requisitos propostos pelos utilizadores merecerem atenção por parte do organizador, alguns deles acabam por não ser aceites, muitas vezes devido a dificuldades de implementação relacionadas com o modo como está estruturado o código do programa.

[](Assignment2/current_issues.png)
Motivação: Os requisitos apresentados são marioritamente funcionais e representam funcionalidades secundárias que apenas melhoram a experiência do utilizador.

[](Assignment2/current_pullrequests.png)

O proprietário enumera uma série de ... : serão apenas aceites se o código estiver devidamente formatado e organizado segundo uma determinada nomenclatura e estilo de código que devem ser obedecidos (também definidas pelo proprietário no documento). 

##Análise Crítica

Os conceitos abordados nas aulas teóricas dizem respeito a projetos de *software* comercial. No entanto, estes conceitos não se aplicam na totalidade a um projeto comunitário sem fins lucrativos como este aqui estudado, fundamentado no *open-source*, sem um processo de desenvolvimento de *software* bem definido.

A categorização dos *issues* recorrendo a etiquetas facilita os processos de validação dos mesmos, constribuindo para uma maior eficácia na detecção de *bugs*.
