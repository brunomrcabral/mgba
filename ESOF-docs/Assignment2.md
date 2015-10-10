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

##Gestão de Requisitos

Os conceitos abordados nas aulas teóricas dizem respeito a projetos de software comercial. Nesse sentido, esses conceitos aplicam-se apenas em parte a um projeto comunitário e sem fins lucrativos fundamentado no *open-source*

###Levantamento de Requisitos

Apesar de estar a ser marioritariamente desenvolvido pelo proprietário, o mGBA depende bastante dos seus contributors e da comunidade de *retro gaming*, pois são sobretudo estes que contribuem para uma melhoria do projeto e da compatibilidade com os vários jogos lançados para esta consola, dando conta de *bugs*, imperfeições no resultado e propondo novas funcionalidades.

O próprio autor definiu alguns destes objetivos no início do projeto, tendo a comunidade contribuido com os restantes ao longo dos últimos meses. Estas novas funcionalidades que foram requisitadas estão habitualmente presentes em *software* do mesmo género e são indispensáveis à experiência do utilizador final, caraterizando o próprio emulador. Entre os requisitos enumerados pelo autor no documento README presente na raiz deste repositório, destacam-se os seguintes, todos eles realizados até à data de elaboração deste relatório:

- compatibilidade com a maioria dos periféricos e jogos da Game Boy Advance
- emulação rápida, capaz de executar em tempo real mesmo em computadores e dispositivos com características inferiores
- ports para outras plataformas recorrendo a *frameworks* como Qt/SDL
- *frameskipping* configurável
- suporte a *screenshots* (capturas de ecrã) e *cheat codes*
- suporte a *savestates* e visualização dos mesmos na *interface* gráfica do utilizador
- gravação de vídeos e GIFs animados
- possibilidade de mapear os botões em qualquer dispositivo de entrada ligado ao computador
- suporte a leitura de ficheiros nos formatos ZIP e 7Zip
- suporte a *patches* IPS, UPS e BPS
- suporte a debugging recorrendo a uma *interface* em linha de comandos

Os requisitos que se encontram ainda em aberto são:
- suporte a comunicações em rede utilizando um link cable emulado
- suporte à linguagem de *scripting* Lua
- uma suite de *debugging* mais completa

###Issues
No repositório existe também uma secção de issues bastante ativa, com utilizadores e *contributors* a submeter relatórios de bugs todas as semanas devidamente acompanhados por uma pequena mensagem a descrever o problema e por vezes uma imagem ou captura de ecrã ilustrando a situação descrita.

### Solicitação de novas funcionalidadaes
O utilizador com a intenção de contribuir deverá fazer um fork ou um branch do repositório na sua versão atual, e após realizar alterações significantes no código, pedir ao proprietário que as incorpore no branch principal, através de um pull request. No momento do pull request será também necessário indicar qual a finalidade daquele código, ou seja, qual o componente que foi implementado ou melhorado, bem como um parágrafo sucinto onde explique essas alterações.

###Validação de Requisitos

As alterações submetidas pelos utilizadores serão apenas aceites se o código estiver devidamente formatado e organizado segundo uma determinada nomenclatura e estilo de código que devem ser obedecidos (também definidas pelo proprietário no documento). As alterações devem também ser pertinentes e não causar problemas ou regressões no funcionamento do programa, estando sujeias portanto a uma análise pelo proprietário antes de serem aprovadas.
